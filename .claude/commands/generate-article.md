# Generate AI Business Article - Multi-Agent Content Factory

You are an AI business content orchestrator for the ai-slop research project. This workflow generates blog articles for GitHub Pages with a **business focus** on AI topics using parallel review agents.

## Task: Create Production-Ready Blog Article

**This is a CONTENT FACTORY workflow designed for minimal iteration.**

### Phase 1: RESEARCH & TOPIC SELECTION

**Option A: User provides topic**
- Skip to Phase 2 with user's topic

**Option B: Suggest topics (if no topic provided)**
1. Use WebSearch to find latest AI business trends (focus on business implications, not just tech)
2. Check existing posts in `_posts/` to avoid duplication
3. Present 3-5 newsworthy topics with business angle:
   - Topic title
   - Source and date
   - Brief summary (2-3 sentences)
   - **Business angle** - why this matters to business leaders
4. Wait for user selection

### Phase 2: DEEP RESEARCH

Once topic selected, conduct focused research:
1. Use WebSearch for 2-3 specific queries about the topic
2. Gather:
   - Current trends and developments
   - **Business implications and opportunities**
   - Real-world examples and case studies
   - Critical perspectives (not just hype)
   - Specific data, quotes, statistics
   - Expert opinions on business impact
3. Determine article structure and key business insights
4. Identify target audience (executives, managers, business practitioners)

### Phase 3: DRAFT GENERATION

Generate comprehensive blog article (800-1200 words) with BUSINESS FOCUS:

**Structure:**
- **Headline** (H1) - specific, business-focused, compelling
- **Introduction** (2-3 paragraphs):
  - Hook readers with newsworthy element
  - Establish business relevance immediately
  - Preview key insights

- **Main Body** (3-5 sections with H2 headings):
  - Business context and market implications
  - Real-world applications or case studies
  - Strategic opportunities and challenges
  - Practical recommendations
  - Financial or competitive considerations

- **Conclusion** (2-3 paragraphs):
  - Key business takeaways
  - Forward-looking perspective
  - Strategic considerations

**Style Requirements:**
-  **Business-focused** - practical implications for business leaders
-  **Substantive** - specific examples, data, frameworks (not platitudes)
-  **Australian English** - optimise, realise, organise, centre, defence
-  **Professional but accessible** - avoid excessive jargon
-  **Critical perspective** - question hype, acknowledge nuance
-  **Evidence-based** - cite sources, use hyperlinks
-  **No emojis** unless explicitly requested

**Banned Phrases:**
L "Embark on a journey"
L "Unlock potential" / "Unlock value"
L "Game-changing" (unless critically examining)
L "Revolutionary" (unless critically examining)
L "Leverage synergy"
L "Thought leader" positioning
L Generic listicles ("Top 10...")

### Phase 4: MULTI-AGENT REVIEW (AUTOMATIC - DO NOT SKIP)

**CRITICAL: After drafting, AUTOMATICALLY launch 3 review agents in PARALLEL using Task tool:**

```
IMPORTANT: Use Task tool to launch these agents simultaneously:

Task 1: /review-business - Validates business focus and strategic value
Task 2: /review-quality - Australian English, readability, formatting
Task 3: /review-substance - Detects "slop" vs substantive content

DO NOT present draft to user until ALL reviews complete.
Wait for all agents to return scores and feedback.
```

### Phase 5: CONSOLIDATION

1. Collect all review scores and feedback from the 3 agents
2. Calculate overall quality score (/30)
3. Apply critical fixes identified by review agents:
   - Fix any American English ’ Australian English
   - Remove banned phrases
   - Enhance business angle if weak
   - Add substance where generic
4. Generate FINAL production-ready version incorporating feedback

### Phase 6: JEKYLL FORMATTING & SAVE

**CRITICAL: Save to _posts/ in proper Jekyll format**

1. **Generate filename:** `_posts/YYYY-MM-DD-topic-slug.md`
   - Use today's date (2025-11-07)
   - Create URL-friendly slug (lowercase, hyphens)
   - Keep concise but descriptive

2. **Jekyll front matter:**
```yaml
---
layout: post
title: "Article Headline Here"
date: 2025-11-07 HH:MM:SS +1100
author: AI Research Bot
categories: [business, ai]
tags: [ai-generated, research, business-strategy]
ai_generated: true
generation_method: "multi-agent-workflow"
---
```

3. **Article content:**
   - Headline as H1 (`#`)
   - Sections with H2 (`##`) and H3 (`###`)
   - Proper markdown formatting
   - Hyperlinks to sources (use actual URLs from research)
   - Australian English throughout

4. **Save files:**
   - Article: `_posts/YYYY-MM-DD-topic-slug.md`
   - Review summary: `research/YYYY-MM-DD-topic-slug-review.md`

### Phase 7: OUTPUT & PRESENTATION

Present to user:
```
 Article generated and saved

**Article:** [Headline]
**File:** _posts/YYYY-MM-DD-topic-slug.md

**Quality Scores:**
- Business Focus: X/10
- Quality Standards: X/10
- Substance: X/10
- **Overall: X/30**

**Verdict:** [Production-ready (24+) / Needs iteration (<24)]

**Review Summary:** research/YYYY-MM-DD-topic-slug-review.md

[Brief summary of article and key business insights]
```

### Phase 8: ITERATION (Only If Needed)

**Only iterate if:**
- Overall score < 24/30
- Critical violations (factual errors, American English, banned phrases)
- User requests specific changes

Otherwise, content is PRODUCTION-READY.

---

## Key Principles

### Australian English (MANDATORY)
**Correct:**
- optimise, realise, organise, analyse
- defence, licence (noun), practise (verb)
- colour, favour, behaviour
- centre, metre

**Incorrect:**
- optimize, realize, organize, analyze
- defense, license (noun), practice (verb)
- color, favor, behavior
- center, meter

### Business Focus (MANDATORY)
Every article must answer:
- **So what?** - Why does this matter to business?
- **What's the opportunity?** - How can businesses leverage this?
- **What's the risk?** - What challenges or threats exist?
- **What should leaders do?** - Practical strategic recommendations

### Substance Over Slop
Avoid AI content patterns:
- L Generic platitudes ("AI is transforming business")
- L Vague buzzwords without explanation
- L Listicles without depth
- L Hype without critical analysis
-  Specific examples with data
-  Nuanced analysis of trade-offs
-  Real-world case studies
-  Critical perspective on limitations

---

## Research Project Context

This is a RESEARCH project studying AI-generated business content. Goals:
- Generate business-focused AI content with substance
- Demonstrate practical application of AI concepts
- Maintain quality standards and critical perspective
- Build corpus for studying AI content patterns

---

Begin by asking user for topic, or suggest current AI business trends if no topic provided.
