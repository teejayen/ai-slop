# Blog Post Guidelines - AI Business Slop Research

**Version:** 1.0
**Date:** 2025-11-07

This document outlines the quality standards and guidelines for AI-generated blog articles in this research project.

---

## Project Mission

Generate AI-focused blog content with:
- **Business perspective** - practical implications for business leaders
- **Substantive depth** - specific examples, data, critical analysis
- **Quality standards** - Australian English, professional formatting
- **Research focus** - studying patterns of AI content generation

---

## Australian English Requirements

###  Correct Australian English

**-ise endings:**
- optimise, realise, organise, analyse
- recognise, emphasise, prioritise, specialise
- characterise, standardise, utilise

**-our endings:**
- colour, favour, behaviour, honour
- labour, endeavour, neighbour

**-re endings:**
- centre, metre, litre, theatre

**-ce/-se distinctions:**
- defence, offence, licence (noun), practise (verb)

### L Incorrect (American English)

**-ize endings:**
- optimize, realize, organize, analyze
- recognize, emphasize, prioritize, specialize
- characterize, standardize, utilize

**-or endings:**
- color, favor, behavior, honor
- labor, endeavor, neighbor

**-er endings:**
- center, meter, liter, theater

**-se/-ce distinctions:**
- defense, offense, license (noun), practice (verb)

---

## Banned Phrases

These phrases signal generic AI content and must be avoided:

### Corporate Jargon
L "Embark on a journey"
L "Unlock potential" / "Unlock value"
L "Leverage synergy"
L "Low-hanging fruit"
L "Move the needle"
L "Circle back"
L "Touch base"
L "Take it offline"

### Overused Tech/Business Phrases
L "Game-changing" (unless critically examining the claim)
L "Revolutionary" (unless critically examining the claim)
L "Paradigm shift"
L "Thought leader" / "Guru" (positioning)
L "The future of X is here"
L "X will change everything"

### Generic AI Slop Markers
L "In today's rapidly evolving landscape..."
L "As we move into the future of..."
L "It's no secret that..."
L "Studies show..." (without specific citation)
L "Experts agree..." (without naming experts)
L "By leveraging..." / "By harnessing..."

---

## Content Quality Standards

### Business Focus

Every article must answer:
- **So what?** - Why does this matter to business?
- **What's the opportunity?** - How can businesses leverage this?
- **What's the risk?** - What challenges or threats exist?
- **What should leaders do?** - Practical strategic recommendations

### Substance Over Slop

** Substantive Content:**
- Specific companies, products, technologies named
- Concrete data points, statistics, metrics
- Real-world examples with details
- Named sources and citations
- Critical perspective on limitations
- Nuanced analysis of trade-offs
- Original insights or synthesis

**L Generic "Slop" Patterns:**
- Vague statements without specifics
- Platitudes and generic predictions
- Uncritical hype repetition
- "Many experts believe..." without naming them
- No concrete examples or data
- Surface-level description only
- Repeating press release content
- Listicles without depth

---

## Article Structure

### Required Elements

**Front Matter (Jekyll format):**
```yaml
---
layout: post
title: "Specific, Compelling Headline (8-12 words)"
date: YYYY-MM-DD HH:MM:SS +1100
author: AI Research Bot
categories: [business, ai]
tags: [ai-generated, research, relevant-tags]
ai_generated: true
generation_method: "multi-agent-workflow"
---
```

**Article Structure:**
1. **Headline (H1)** - Specific, business-focused, compelling
2. **Introduction (2-3 paragraphs)**
   - Hook with newsworthy element
   - Establish business relevance
   - Preview key insights
3. **Main Body (3-5 sections with H2 headings)**
   - Business context and implications
   - Real-world applications or examples
   - Strategic opportunities and challenges
   - Practical recommendations
4. **Conclusion (2-3 paragraphs)**
   - Key business takeaways
   - Forward-looking perspective
   - Strategic considerations

### Length & Formatting

- **Word count:** 800-1200 words
- **Paragraph length:** 2-5 sentences
- **Heading hierarchy:** H1 for title, H2 for sections, H3 for subsections
- **No emojis** (unless explicitly requested)
- **Hyperlinks** to sources and references
- **Proper markdown** formatting

---

## Multi-Agent Review Process

Every article is reviewed by 3 specialized agents:

### 1. Business Focus Agent (/review-business)
**Scores:** /10

Evaluates:
- Business relevance and practical value
- Strategic insights and recommendations
- Target audience alignment (business leaders)
- Real-world business examples

### 2. Quality Standards Agent (/review-quality)
**Scores:** /10

Evaluates:
- Australian English compliance (critical)
- Banned phrase detection
- Blog formatting and structure
- Readability and accessibility

### 3. Substance Agent (/review-substance)
**Scores:** /10

Evaluates:
- Specificity vs vagueness
- Critical perspective vs uncritical hype
- Depth of analysis vs surface-level
- Evidence and sourcing

### Overall Quality Score

**Total: /30**

- **27-30:** Exceptional - publish as-is
- **24-26:** Production-ready - minor notes only
- **20-23:** Good - consider iteration
- **< 20:** Needs revision

---

## Writing Style

### Voice & Tone
- **Professional but accessible** - avoid excessive jargon
- **Critical and analytical** - not cheerleading or hype
- **Evidence-based** - cite sources and data
- **Business-focused** - practical implications
- **Balanced** - acknowledge limitations and challenges

### Best Practices
-  Use active voice
-  Vary sentence length
-  Name specific companies/products/people
-  Cite sources with hyperlinks
-  Explain technical terms
-  Provide concrete examples
-  Question hype and marketing claims
-  Discuss trade-offs and challenges

### Avoid
- L Generic platitudes
- L Vague buzzwords
- L Uncritical hype
- L Unsupported claims
- L Excessive jargon
- L One-sided cheerleading
- L Formulaic AI patterns

---

## Research & Sourcing

### Required Research
- Use WebSearch for current trends and developments
- Find 2-4 credible sources
- Gather specific data, quotes, examples
- Identify real-world applications and case studies
- Seek critical perspectives and limitations

### Source Quality
- **Preferred:** Research papers, tech publications, company announcements, industry reports
- **Acceptable:** Reputable tech news sites, expert blogs, trade publications
- **Avoid:** Press releases without analysis, marketing content, unverified claims

### Citation Standards
- Link to original sources where possible
- Name specific studies, reports, companies
- Attribute quotes and statistics
- Distinguish fact from speculation

---

## Topics & Coverage

### Good Topics
 Specific AI developments with business implications
 Real-world AI implementations and outcomes
 Strategic challenges in AI adoption
 Market trends backed by data
 Critical analysis of AI hype
 Business model implications of AI

### Topics to Avoid
L Generic "What is AI?" content
L Listicles without depth
L Purely technical content without business angle
L Old news (>2 weeks unless groundbreaking)
L Speculation without evidence
L Content that duplicates recent posts

---

## File Organization

### Article Files
- **Location:** `_posts/YYYY-MM-DD-topic-slug.md`
- **Naming:** Use lowercase, hyphens, descriptive slug
- **Format:** Jekyll markdown with front matter

### Review Files
- **Location:** `research/YYYY-MM-DD-topic-slug-review.md`
- **Content:** Agent scores, feedback, generation notes
- **Purpose:** Document process and patterns

---

## Quality Assurance Checklist

Before publishing, verify:
- [ ] Australian English throughout (no American spellings)
- [ ] No banned phrases
- [ ] Business angle clearly articulated
- [ ] Specific examples and data included
- [ ] Sources cited with hyperlinks
- [ ] Critical perspective present (not just hype)
- [ ] Proper Jekyll front matter
- [ ] H1/H2/H3 heading hierarchy
- [ ] 800-1200 word count
- [ ] All agent scores e24/30 total

---

## Research Project Goals

Remember, this project studies AI content generation patterns to:
- Understand what differentiates substance from "slop"
- Document business-focused AI content approaches
- Maintain quality standards in automated generation
- Provide examples of responsible AI content creation
- Build corpus for analyzing AI writing patterns

**All content is clearly labeled as AI-generated for research purposes.**

---

**Last Updated:** 2025-11-07
**Next Review:** Monthly calibration recommended
