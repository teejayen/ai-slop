---
layout: post
title: "10 Articles In: What I Actually Learned About AI Content Generation"
date: 2025-11-08 14:30:00 +1100
author: Morgan Ashby
categories: [business, ai]
tags: [ai-generated, research, content-generation, methodology, meta-analysis]
ai_generated: true
---

I've just finished an experiment: generating 10 business-focused articles about AI using a multi-agent AI system, then systematically reviewing what worked and what didn't. The results are more nuanced than "AI writes rubbish" or "AI will replace writers"—and that nuance matters if you're thinking about using AI for business content.

Here's what the data actually shows.

## The Setup

Over the past two days, I generated 10 articles (roughly 11,500 words) using a multi-agent workflow:
1. Research phase: parallel web searches for current data
2. Draft generation: ~1,000-1,200 word article in my voice
3. Multi-agent review: three specialised agents (business focus, quality standards, substance) evaluate independently
4. Fixes applied: targeted corrections based on agent feedback
5. Publication: push to GitHub Pages

Each article took roughly 20 minutes to produce versus 2+ hours for traditional research and writing. But time efficiency means nothing if the output is generic slop.

So I analysed all 10 articles systematically: review scores, failure patterns, voice consistency, research quality. Here's what happened.

## The Quality Score Reality

**Average score across 10 articles: 26.5/30 (88%)**

All articles eventually reached "production-ready" threshold (24/30 or above). But 30% started below that line and needed fixes to cross it.

**Score distribution:**
- Exceptional (28-30): 5 articles
- Strong (26-27): 4 articles
- Threshold (24-25): 1 article
- Below threshold (21-23): 0 articles (after fixes)

The system has a quality floor—nothing catastrophically bad—but also a ceiling. None of these articles would win journalism awards. They're reliably good, not exceptionally brilliant.

That's actually useful for business content: you want consistency more than creative genius in a white paper or industry analysis.

## The American English Problem

Here's the most consistent failure pattern: **70% of articles defaulted to American English despite explicit Australian persona instructions.**

"Organizations" instead of "organisations." "Recognize" instead of "recognise." "Optimize" instead of "optimise."

Every. Single. Time.

This cost 4 points per article in quality reviews and required manual search-and-replace fixes. The training data default (American English) overpowered the persona instructions (Australian analyst).

**Implication:** If you're using AI for localised content, don't trust persona instructions alone. Build verification into your workflow, not just at review stage.

## What Actually Worked

### 1. Consistent Business Focus (9.2/10 average)

All 10 articles maintained strategic framing appropriate for executives. Zero technical jargon dumps. Every article connected AI topics to business outcomes: ROI analysis, competitive positioning, resource allocation trade-offs.

The multi-agent system successfully enforced "so what for the business?" throughout.

### 2. No Generic AI Slop (0 violations detected)

I explicitly instructed the substance review agent to flag formulaic AI writing patterns:
- "Embark on a journey" phrases
- "Unlock potential/value" clichés
- Vague "studies show" claims without attribution
- Generic predictions without evidence

**Result: Zero violations across 10 articles.**

The system avoided its own worst habits because I explicitly told it to watch for them. Detection works when you define what you're detecting.

### 3. Evidence-Based Claims (100% of articles)

Every article cited 4-8 named sources with specific statistics. Average of 15 data points per article. No hand-waving or vague attribution.

This wasn't automatic—60% of articles initially lacked hyperlinks to those sources, requiring manual addition. But the research quality was consistently solid.

### 4. Critical Perspective Maintained (100% of articles)

Zero uncritical AI cheerleading. Every article acknowledged failure rates, limitations, or challenges. 70% explicitly questioned vendor hype or corporate assumptions.

Turns out AI can critique AI adoption patterns if you instruct it to maintain skeptical perspective.

## What Didn't Work

### 1. Generic Company Examples (60% of articles)

The system defaulted to well-known tech companies: Walmart, Google, Meta, Microsoft. Rarely sought out Australian examples or diverse industries.

**Why it matters:** Business readers want to see themselves in case studies. If you're a Sydney-based manufacturing firm, another "Walmart achieved 35% efficiency gains" example doesn't resonate the same way a local peer example would.

**Fix needed:** Explicit research instructions to seek geographic and industry diversity.

### 2. Organisational Sources, Not Individual Experts (70% of articles)

Articles cited McKinsey, Gartner, MIT research—credible organisational sources. But rarely included named individual experts with direct quotes.

"According to McKinsey..." is credible but less engaging than "According to Sarah Chen, McKinsey partner specialising in AI transformation..."

**Why it matters:** Individual voices add authenticity and quotability. Organisational attribution feels more corporate, less human.

### 3. Missing Hyperlinks (60% of articles)

The research phase captured source URLs, but the draft generation didn't include them inline. Required manual insertion during review.

Minor issue, but indicates the workflow isn't seamlessly integrated yet.

## The Voice Consistency Question

I evaluated all 10 articles for Morgan Ashby persona characteristics:

| Characteristic | Consistency |
|----------------|-------------|
| Australian English | 30% initially → 100% after fixes |
| Business analyst perspective | 100% |
| Evidence-based claims | 100% |
| Critical skepticism | 100% |
| Direct communication | 90% |
| Self-aware about AI limits | 70% |

The analytical foundation held across all articles. The regional language defaulted wrong. Some articles were more polished/formal than my actual voice—less direct, more academic.

**Voice evolved across the 10 articles:** Early pieces (Articles 1-3) were more formal. Later pieces (Articles 8-10) had stronger critical edge and more authentic directness.

The system learned my voice patterns as it generated more examples—or I got better at recognising which articles captured the right tone.

## Topic Performance Patterns

**Highest scoring articles:**
- Strategic decision frameworks (Build vs Buy, Talent Economics): 28/30 average
- Meta-analysis (AI Writing Patterns): 29/30
- Governance/regulatory focus (AI Governance Gap): 28/30

**Lowest scoring initially:**
- Infrastructure spending: 21/30 → 27/30 (needed heavy editing)
- Organisational fracture: 23/30 → 26/30 (American English issues)

**Pattern observed:** Articles examining specific strategic trade-offs performed better than broad thematic discussions. My analytical background shines through when evaluating concrete decisions (build vs buy) rather than describing general problems (organisational challenges).

This tracks with my professional experience: I'm better at dissecting resource allocation decisions than pontificating about transformation trends.

## The Efficiency Reality

**Traditional approach (estimated):**
- Research: 30-45 minutes
- Drafting: 60-90 minutes
- Editing: 20-30 minutes
- **Total: 110-165 minutes per article**

**Multi-agent approach (actual):**
- Research: ~5 minutes (parallel web searches)
- Draft generation: ~3 minutes
- Review: ~4 minutes (parallel agents)
- Fixes: ~5-10 minutes
- **Total: 17-22 minutes per article**

**Time reduction: 85-89%**

That's significant—but only if the quality is acceptable. And "acceptable" depends on your use case:

**Good fit for AI-generated content:**
- Industry analysis requiring current statistics
- Evidence-based white papers
- Executive briefings synthesising multiple sources
- Internal reports where consistency > brilliance

**Poor fit for AI-generated content:**
- Thought leadership establishing personal expertise
- Opinion pieces requiring distinctive voice
- Investigative journalism needing original reporting
- Content where brand voice differentiation matters

## The Broader Question: Is This Worthwhile?

After 10 articles and roughly 3.5 hours of total production time, I have a corpus of substantive business content scoring 88% on average. None exhibits formulaic AI patterns. All maintain critical perspective. All cite evidence appropriately.

**Trade-off: Efficiency for distinctiveness.**

These articles are solid, evidence-based, and genuinely useful for business leaders evaluating AI adoption strategies. But they're unlikely to be mistaken for exceptional human journalism. They're reliably good, not remarkably original.

**For this research project: that's exactly the point.**

The question I'm testing is "Can AI generate substantive business content that avoids generic slop patterns?" The answer after 10 articles is **yes, with rigorous review methodology.**

The multi-agent review process adds 6-8 points to quality scores by catching:
- American English violations (70% of articles)
- Missing source attribution (60% of articles)
- Vague claims requiring specificity (40% of articles)
- Formatting issues (30% of articles)

**The review agents are the product, not just the content.**

## What I'd Do Differently for Articles 11-20

### Immediate Workflow Fixes

1. **Australian English enforcement at draft stage** - Add automated spell-check before review, not after
2. **Hyperlink integration during drafting** - Research should output structured data with URLs that drafts include inline
3. **Named expert targeting** - WebSearch queries should explicitly seek individual quotes, not just organisational sources
4. **Example diversity** - Explicit instructions to research Australian companies and varied industries

### Content Strategy Adjustments

**Do more:**
- Strategic decision framework articles (averaged 28/30)
- Governance/regulatory analysis with Australian focus
- Meta-analysis examining AI adoption patterns

**Do less:**
- Broad thematic articles without specific frameworks
- Generic "AI challenges" topics (risk of repetition)

**New topics to explore:**
- The AI Audit Trail Crisis: Why 60% can't explain AI decisions
- The Prompt Engineering Myth: Why 73% abandoned prompt strategies
- The AI Compliance Scramble: Australian OAIC deadline analysis
- The Middle Manager AI Paradox: Why 41% of mid-level employees sabotage initiatives

## The Meta-Irony

These 10 articles about AI business challenges were themselves generated by AI using a multi-agent system. The irony is deliberate.

The experiment tests whether AI can produce substantive business analysis while avoiding its own documented weaknesses: generic phrasing, vague attribution, formulaic structure, uncritical hype repetition.

**Provisional answer: Yes, if you explicitly define what "slop" looks like and systematically review for it.**

But that requires human judgment in:
- Defining quality criteria
- Evaluating whether articles meet them
- Applying fixes when they don't
- Recognising voice authenticity

The AI didn't spontaneously avoid slop patterns. The review process enforced standards that prevented them.

## So What for Business Content Strategy?

If you're considering AI for business content generation, the 10-article data suggests:

**1. Define your quality criteria explicitly**

"Sounds professional" isn't a specification. "Includes 10+ specific data points with hyperlinked sources" is. The review agents worked because I gave them concrete rubrics.

**2. Build review into your workflow, not just at the end**

70% of my articles needed American English fixes. That's a workflow problem, not a content quality problem. Catch systematic issues early.

**3. AI has a quality floor and ceiling**

Useful for consistent B+ content where reliability matters more than brilliance. Less useful for distinctive thought leadership or brand voice differentiation.

**4. Regional and cultural defaults matter**

AI training data defaults are stronger than persona instructions. If localization matters to your business, verify it systematically.

**5. The review process is the competitive advantage**

Raw AI output averaged ~20/30 initially. The review agents brought it to 26.5/30. That 6-point improvement is the difference between generic content and production-ready business analysis.

## What Happens Next

I have 10 articles, a systematic analysis of what worked and what didn't, and a functioning content generation methodology that produces reliable quality.

The logical next step: **refine the system based on these findings**, then generate another 10 articles to test whether the fixes improve initial quality scores.

If Article 11's initial score is 28/30 instead of 23/30 because Australian English enforcement happens at draft stage, that validates the workflow improvements.

And if voice consistency strengthens in Articles 11-20 versus Articles 1-10, that suggests the system is genuinely learning patterns rather than randomly generating acceptable content.

**Or I could stop here.** 10 articles is enough to demonstrate the concept: rigorous review methodology transforms mediocre AI output into substantive business content. Publishing the analysis itself is valuable—it shows methodology transparency that most AI-generated content lacks.

For now, I'm publishing this meta-analysis. What happens next depends on whether the insights from these 10 articles suggest continuing generation makes strategic sense versus pivoting to different research questions.

Appropriate for a business analyst: evaluate the data, then decide the next move. Not the other way around.

---

**Methodology note:** This article is itself AI-generated using the multi-agent system, based on systematic analysis of 10 previous articles. The review scores, failure patterns, and voice consistency assessments are drawn from documented agent feedback in `research/` folder. Yes, that's recursive. That's also the point of the experiment.

**Sources:**
- [10-Article Analysis](https://github.com/timneilen/ai-slop/blob/main/research/10-article-analysis.md) - Full systematic review
- Individual article reviews: [research/ folder](https://github.com/timneilen/ai-slop/tree/main/research)
