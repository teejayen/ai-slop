---
layout: post
title: "Prompt Caching: Why Your LLM App Might Be Wasting 90% of Its API Budget"
date: 2025-11-08 22:00:00 +1100
author: Technical Team
categories: [technical, ai]
tags: [ai-generated, llm, optimization, caching, developers]
ai_generated: true
---

If you're building an LLM application that sends the same system prompts, RAG context, or few-shot examples with every request, you're likely paying 10x more than necessary.

[Prompt caching](https://docs.claude.com/en/docs/build-with-claude/prompt-caching) is a server-side optimization that lets LLM providers store and reuse the computational state of static prompt segments across requests. According to [AWS implementation data](https://newsletter.simpleaws.dev/p/amazon-bedrock-prompt-caching), cached content processes up to 85% faster whilst costing approximately 90% less than uncached tokens.

Most developers aren't using it. Here's why that's expensive, and how to fix it.

## The Problem: Redundant Processing at Scale

Consider a typical RAG application:

```
System prompt (500 tokens) +
Retrieved documents (3,000 tokens) +
Few-shot examples (1,500 tokens) +
User query (50 tokens) = 5,050 tokens per request
```

Without caching, every request processes all 5,050 tokens as input, even though 98% (the first 5,000 tokens) remains identical across requests.

**At scale:** 10,000 requests/day × 5,050 tokens = 50.5 million input tokens processed

**With caching:** 10,000 requests × 50 tokens = 500,000 tokens + initial cache write of 5,000 tokens

**Cost difference:** ~99% reduction in redundant processing

## How Prompt Caching Actually Works

[Prompt caching stores the intermediate computational state](https://www.datacamp.com/tutorial/prompt-caching) associated with the static prefix of your prompt. When you send a subsequent request with the same prefix, the LLM provider retrieves the cached state instead of recomputing embeddings and attention patterns.

**Under the hood:**
1. Provider identifies static prompt segments (marked explicitly or detected automatically)
2. Computes and stores intermediate layer activations
3. On cache hit, reuses stored state and processes only new tokens
4. Cache typically expires after 5-10 minutes of inactivity

**Key constraint:** [Cached tokens only activate if the first 1,024+ tokens match exactly](https://apidog.com/blog/what-is-prompt-caching/) between requests. Even single-character differences invalidate the cache.

## Provider Implementation Differences (2025)

### OpenAI: Automatic Caching

[GPT-4o and GPT-4o mini handle caching automatically](https://platform.openai.com/docs/guides/prompt-caching) for prompt prefixes exceeding 1,024 tokens.

**Implementation:** Zero code changes required

**Pricing:**
- Cached token reads: ~50% discount vs standard input tokens
- Cache writes: Standard input token pricing

**Limitations:** No explicit control over what gets cached (automatic detection only)

### Anthropic Claude: Explicit Control

[Claude models require explicit cache block markers](https://docs.claude.com/en/docs/build-with-claude/prompt-caching) using API parameters.

**Implementation:** Mark content blocks with `cache_control` parameter

```python
{
  "model": "claude-3-5-sonnet-20241022",
  "system": [
    {"type": "text", "text": "System instructions...", "cache_control": {"type": "ephemeral"}}
  ]
}
```

**Pricing:**
- Cache writes: ~25% premium vs standard input tokens
- Cache reads: ~90% discount vs standard input tokens

**Advantage:** Explicit control over caching boundaries

### Amazon Bedrock: Model-Specific Support

[As of April 2025, only Claude 3.5 Haiku, Claude 3.7 Sonnet, and Nova models support caching](https://newsletter.simpleaws.dev/p/amazon-bedrock-prompt-caching) on Bedrock.

**Implementation:** Same Claude API syntax via Bedrock

**Pricing:** Nova models have no cache write charges (as of March 2025); third-party models follow Claude pricing

## Optimization Patterns That Actually Work

### 1. Structure Prompts for Maximum Cache Hits

**Don't:** Interleave static and dynamic content
```
User query → System prompt → RAG docs → Few-shot examples (cache miss every time)
```

**Do:** Front-load all static content
```
System prompt → RAG docs → Few-shot examples → User query (cache hit after first request)
```

**Rationale:** Caching requires prefix matching. Static content must be contiguous from position 0.

### 2. Batch Similar Requests to Extend Cache Lifetime

Caches expire after 5-10 minutes of inactivity. For applications with variable request patterns:

**Strategy:** Route similar query types to dedicated workers that maintain hot caches

**Example:** RAG applications with multiple document collections—separate workers per collection keep relevant document caches warm

**Impact:** [DataCamp analysis](https://www.datacamp.com/tutorial/prompt-caching) shows 3-5x cache hit rates with request routing vs random distribution

### 3. Optimise Cache Write Frequency

Cache writes cost 10-25% more than standard input processing. For frequently-changing context:

**Calculate break-even:** If content changes more often than it's reused 4-10 times, caching costs more than it saves

**Solution:** Version prompts explicitly and cache only stable versions

```python
# Bad: Cache invalidation on every minor edit
prompt_v1 = "Instructions... [updated: 2025-11-08]"

# Good: Semantic versioning for cache stability
prompt_v2 = "Instructions version 2.0"  # Cache until v3.0
```

### 4. Measure Cache Hit Rates, Not Just Cost

Low cache hit rates indicate structural problems:
- Dynamic content in cached prefix
- Cache expiration due to inactivity
- Prompt variations breaking prefix matching

**Monitoring:** Track `cache_creation_input_tokens` vs `cache_read_input_tokens` in API responses

**Target:** >80% hit rate for applications with stable system prompts/RAG context

## Real-World Performance Data

### Cost Reduction

[According to Anthropic documentation](https://docs.claude.com/en/docs/build-with-claude/prompt-caching), applications with large static contexts achieve:
- **RAG applications:** 85-95% cost reduction (large document contexts reused frequently)
- **Few-shot prompting:** 70-85% reduction (multiple examples in every request)
- **Agentic workflows:** 60-75% reduction (complex system prompts with tool definitions)

### Latency Improvement

[AWS measurements show](https://newsletter.simpleaws.dev/p/amazon-bedrock-prompt-caching) cached requests process 85% faster for large prefixes (5,000+ tokens).

**Typical latency impact:**
- Uncached: 3,000 tokens @ 800 tokens/sec = 3.75 seconds processing time
- Cached: 50 tokens @ 800 tokens/sec = 0.06 seconds processing time

**Result:** 98% latency reduction for cached portion

## When Prompt Caching Doesn't Help

### Anti-Patterns

**1. Highly dynamic prompts**
If system instructions change per-user or per-request, caching provides no benefit. Cache hit rates <20% mean you're paying cache write premiums without reuse savings.

**2. Short prompts**
Minimum cache activation is typically 1,024 tokens. Applications with <1,000 token prefixes see negligible benefits and may lose money on cache write costs.

**3. Low request volume**
With <100 requests/day, cache expiration (5-10 minutes inactivity) prevents reuse. The cache write premium exceeds savings from rare cache hits.

**4. Single-use contexts**
One-off document analysis where each request has unique context. No repeat prefix = no cache hits.

### Calculate Your Break-Even

```python
cache_write_premium = 0.25  # 25% more expensive
cache_read_discount = 0.90   # 90% cheaper

reuses_needed = cache_write_premium / cache_read_discount
# Result: ~3 reuses to break even
```

If your static prefix isn't reused 3+ times before cache expiration, you're losing money.

## Implementation Checklist

For developers adding prompt caching to existing applications:

**1. Audit your prompt structure**
- Identify static vs dynamic segments
- Measure token counts for each segment
- Verify static content is contiguous from position 0

**2. Estimate potential savings**
```python
daily_requests = 10_000
tokens_per_request = 5_000
static_tokens = 4_500  # 90% of prompt is static

# Current cost (hypothetical pricing)
current_cost = daily_requests * tokens_per_request * $0.001/1000 = $50/day

# With caching (after first request)
cache_write = static_tokens * $0.00125/1000 = $0.0056
cache_reads = daily_requests * static_tokens * $0.0001/1000 = $4.50/day
dynamic_processing = daily_requests * 500 * $0.001/1000 = $5/day
cached_cost = $4.50 + $5.00 = $9.50/day

# Savings: $50 - $9.50 = $40.50/day (81% reduction)
```

**3. Implement provider-specific caching**
- OpenAI: No code changes (automatic)
- Anthropic: Add `cache_control` blocks to static content
- Bedrock: Use Anthropic syntax with supported models

**4. Monitor cache performance**
- Track `cache_creation_input_tokens` (writes)
- Track `cache_read_input_tokens` (hits)
- Calculate hit rate: reads / (reads + writes)
- Target: >80% for applications with stable prompts

**5. Optimise for cache stability**
- Version prompts semantically, not with timestamps
- Batch similar requests to maintain hot caches
- Front-load static content for maximum prefix matching

## The Practical Reality

Prompt caching isn't magic—it's a straightforward optimisation for applications with large, repetitive prompt prefixes.

**Where it works:**
- RAG with document collections reused across queries
- Few-shot learning with example sets
- Agentic systems with complex tool definitions
- Customer support with static knowledge base context

**Where it doesn't:**
- Unique documents per request
- Highly personalised prompts
- Low-volume applications
- Short prompts (<1,024 tokens)

**The test:** If you're sending the same 1,000+ tokens in 80%+ of your requests, and your request volume exceeds 100/day, you should be using prompt caching. Otherwise, you're paying 10x more than necessary for redundant processing.

For most production LLM applications with RAG or few-shot patterns, that's 70-90% cost reduction for a few lines of code.

---

**Implementation note:** This article was generated using AI and reviewed by multi-agent systems. All performance data, pricing information, and provider implementation details are cited with source links to official documentation and technical analyses.

**Sources:**
- [Anthropic Claude: Prompt Caching Documentation](https://docs.claude.com/en/docs/build-with-claude/prompt-caching) - Official implementation guide and pricing
- [OpenAI: Prompt Caching Guide](https://platform.openai.com/docs/guides/prompt-caching) - Automatic caching behaviour for GPT-4o models
- [Amazon Bedrock: Prompt Caching Technical Architecture](https://newsletter.simpleaws.dev/p/amazon-bedrock-prompt-caching) - AWS implementation details and performance data
- [DataCamp: Prompt Caching Code Implementation](https://www.datacamp.com/tutorial/prompt-caching) - Technical tutorial with cache hit rate analysis
- [Apidog: What is Prompt Caching?](https://apidog.com/blog/what-is-prompt-caching/) - Best practices and activation thresholds
- [Medium: Prompt Caching Cost Analysis](https://medium.com/@pur4v/prompt-caching-reducing-llm-costs-by-up-to-90-part-1-of-n-042ff459537f) - 90% cost reduction calculations
