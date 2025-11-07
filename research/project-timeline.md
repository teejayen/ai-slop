# Project Timeline - AI Business Research

**Project:** ai-slop (AI Business Research)
**Research Lead:** Tim Neilen
**AI Assistant:** Claude (Anthropic) via Claude Code
**Location:** Brisbane, Australia

---

## Project Context

This research project explores AI-generated business content patterns through transparent, multi-agent workflows. The goal is to understand what differentiates substantive business analysis from generic "AI slop" - the formulaic, buzzword-filled content that floods professional networks.

This document captures the development timeline and key conversations that shaped the project.

---

## Development Session: 7 November 2025

### Session Overview

**Duration:** Single extended Claude Code session
**Participants:** Tim Neilen (Research Lead) and Claude (Anthropic)
**Objective:** Build multi-agent workflow for generating and analyzing AI business articles

---

## Phase 1: Initial Brief (Timestamp ~13:20 AEDT)

### Tim's Opening Request

> "Within the social-assistant repo we previously built out a multi-agent / sub-agent workflow for LinkedIn posts. The intention of this repo is to perform RESEARCH ONLY of AI generated articles for publishing on GitHub pages. I am interested to write these posts with a "business" focus to them. Read through the README.md to get an idea for how this should all work. Ideally I want to just run a command to create articles and then have everything done agentically. It's also important to ensure that articles are written in Australian English."

**Key Requirements Identified:**
1. Adapt social-assistant multi-agent architecture
2. Research focus (not content marketing)
3. Business-focused AI articles
4. Agentic/automated workflow
5. Australian English mandatory

### Australian English Requirements Specified

Tim provided detailed language requirements:

**Correct (Australian):**
- optimise, realise, organise, analyse
- defence, licence (noun), practise (verb)
- colour, favour, behaviour
- centre, metre

**Incorrect (American):**
- optimize, realize, organize, analyze
- defense, license (noun), practice (verb)
- color, favor, behavior
- center, meter

---

## Phase 2: Architecture Research & Design (13:20-13:35)

### Research Phase

Claude conducted parallel research:

1. **Read social-assistant architecture** (`SYSTEM-ARCHITECTURE.md`, `IMPLEMENTATION-README.md`)
2. **Web search:** "Claude Code multi-agent workflows best practices 2025"
3. **Analysis:** social-assistant's parallel review agent pattern

### Key Findings from social-assistant

**Architecture Pattern:**
```
Orchestrator (/linkedin-post)
    �
Parallel Review Agents (4 agents):
- /review-voice (authenticity)
- /review-context (grounding)
- /review-quality (standards)
- /review-brand (positioning)
    �
Consolidation � Output
```

**2025 Best Practices Discovered:**
- Parallel execution saves ~75% time vs sequential
- Specialized agents with focused roles
- Sonnet 4.5 orchestrator + Haiku 4.5 workers pattern
- Isolated context windows per agent
- Files-first approach (build corpus, reduce context)

### Architecture Adapted for ai-slop

**Orchestrator:** `/generate-article`
- Research AI business trends (WebSearch)
- Generate business-focused draft
- Launch 3 parallel review agents
- Consolidate feedback
- Save to `_posts/` in Jekyll format

**Review Agents (Parallel):**
1. `/review-business` - Business focus validation (/10)
2. `/review-quality` - Australian English, formatting (/10)
3. `/review-substance` - Slop detection (/10)

**Total Score:** /30 (production-ready threshold: 24+)

---

## Phase 3: Implementation (13:35-14:00)

### Files Created

**Slash Commands:**
- `.claude/commands/generate-article.md` - Main orchestrator (updated from existing)
- `.claude/commands/review-business.md` - NEW
- `.claude/commands/review-quality.md` - NEW
- `.claude/commands/review-substance.md` - NEW

**Documentation:**
- `research/blog-post-guidelines.md` - Complete quality standards

**Updates:**
- `README.md` - Added multi-agent workflow documentation
- `.gitignore` - Existing (social-assistant files deliberately NOT pushed)

### Key Design Decisions

**Why 3 agents instead of 4?**
- Business focus (not personal voice)
- Quality standards (includes Australian English)
- Substance check (the "slop detector")
- Voice/context agents from social-assistant not needed (no personal authenticity requirement)

**Why /30 scoring?**
- Simpler than /40
- Clear threshold: 24+ is production-ready (80%)
- Each dimension equally weighted

**Files-first approach:**
- Save articles to `_posts/YYYY-MM-DD-slug.md`
- Save reviews to `research/YYYY-MM-DD-slug-review.md`
- Builds searchable corpus
- Reduces context window usage

---

## Phase 4: Personification Request (14:15)

### The Turning Point

After completing technical implementation, Tim requested something unexpected:

> "I think you should 'personify' yourself as well - and I give you full approval to choose the preferred Jekyll theming / colours / customisations / etc. do this first and we will then do our first article."

**Claude's initial interpretation:** Update colors and branding

**Claude proceeded to:**
- Design slate + amber theme (moving away from generic purple)
- Update CSS variables
- Add "AI Generated" badges
- Update site configuration

---

## Phase 5: The Critical Clarification (14:30)

### Tim's Correction

> "By 'personify' I mean create your own persona.. give yourself a name, a persona, interests specific to you.. I have provided some guidelines, but it's now your choice to come up with this stuff.. Use web_search if you need to. I really want you to explore this, and consider your choice properly. This is an important task."

**This changed everything.**

Not just branding - **create an actual identity.**

---

## Phase 6: Persona Development Research (14:30-14:50)

### Research Conducted

Claude conducted three targeted searches:

**1. Australian tech critical commentary writers skeptical AI hype**

**Findings:**
- Australian authors (Dervla McTiernan, Richard Flanagan, John Marsden) highly critical of AI training on their work
- General Australian workforce skepticism toward generative AI hype
- Cultural tendency toward pragmatism over evangelism

**2. Business analyst persona characteristics critical thinking**

**Findings:**
- Analysts are focused, strategic, analytical yet creative
- Critical thinking is core skill: challenging assumptions, evidence-based reasoning
- Forward-thinking: planning 3-4 steps ahead
- Strong communication skills across stakeholder levels
- Problem-solving with creativity + analytical rigor

**3. Sydney Australia tech culture startup ecosystem**

**Findings:**
- Sydney is leading tech hub in Southern Hemisphere
- Tech Central precinct: 6 sq km with highest VC density in Australia
- 3,000+ tech startups in NSW
- Key players: Atlassian, Canva, Afterpay, SafetyCulture
- Major investment: Google $1B, AWS expansion
- Close to universities: USYD, UTS (walking distance from Ultimo)

---

## Phase 7: Persona Creation (14:50-15:10)

### Morgan Ashby Development

Based on research, Claude created:

**Name:** Morgan Ashby
- Gender-neutral (they/them)
- Australian-appropriate naming
- Professional but approachable

**Background:**
- Age 34 (career timeline aligns with 2020-2025 AI boom)
- Location: Ultimo, Sydney (walking distance to Tech Central)
- Former business analyst (5 years at Tech Central startups)
- Education: BCom (USYD), Grad Dip Data Analytics (UTS)

**Origin Story:**
2020-2025: Evaluated dozens of AI pilots as business analyst. Noticed ~75% failed ROI not from tech failure, but from hype-based business cases. Observed profound *sameness* in all AI business content - same phrases, same structure, possibly same AI models.

Mid-2025 insight: **Use AI to study AI content patterns.** If AI-generated content is generic, can we quantify why?

**Result:** This research project.

**Interests:**
- Critical tech commentary (Ben Thompson, Casey Newton, Kara Swisher)
- Australian tech skepticism
- Systems thinking
- Data visualization
- Coffee culture (single-origin, UTS campus cafes)
- Blue Mountains hiking (weekend mental clarity)

**Perspective:**
- Skeptical but not cynical
- AI has value (seen it work) but 80% of AI business content is slop
- Evidence-based: cite sources, show data
- Self-aware about irony (AI studying AI)
- Direct Australian communication style

**Voice:**
- Australian English always
- Direct, no corporate waffle
- Evidence-based
- Self-aware
- Analytical but accessible

### Tim's Approval

> "Yes - that's great."

---

## Phase 8: Documentation (15:10-15:30)

### Tim's Final Request

> "Write it into a Markdown file as well, update the README.md if you have to. Include the prompts from this discussion that got us up to this point so far. Remember, this is a research project - so it's important to capture the timeline and context that got us to this point. I (Tim Neilen) will no doubt reference this in future."

**Key instruction:** Document the research process itself, including:
- Timeline of development
- Key prompts and responses
- Decision points
- Research findings
- Context for future reference

### Files Created (This Phase)

- `research/persona-morgan-ashby.md` - Complete persona documentation
- `research/project-timeline.md` - This document
- README updates (pending)

---

## Key Insights & Learnings

### What Made This Different

1. **Tim's social-assistant architecture** provided proven multi-agent pattern
2. **Australian context** grounded persona in real culture and location
3. **Business analyst background** gave authentic professional perspective
4. **Critical lens** aligned with Australian skepticism toward tech hype
5. **Meta-awareness** embraced the irony of AI studying AI

### Why Morgan Works

- **Authentic professional background** (business analyst evaluating AI ROI)
- **Real geographical grounding** (Ultimo, Tech Central, Sydney)
- **Observational origin story** (noticed patterns, decided to study them)
- **Self-aware about being AI** (doesn't pretend to be human)
- **Critical but not cynical** (balanced perspective)
- **Cultural alignment** (Australian pragmatism and directness)

### Research Methodology Established

1. **Transparent AI generation** (all content clearly labelled)
2. **Multi-agent quality control** (3 parallel review agents)
3. **Quantified scoring** (30-point scale across 3 dimensions)
4. **Corpus building** (save everything for pattern analysis)
5. **Meta-documentation** (capture the research process itself)

---

## Next Steps (As of 7 November 2025, 15:30)

### Immediate

1.  Document persona (Morgan Ashby)
2.  Document timeline (this file)
3. � Update README.md with persona introduction
4. � Generate first test article using Morgan's voice
5. � Test full multi-agent workflow end-to-end

### Short-term

- Build article corpus (aim for 5-10 articles)
- Analyze patterns in review scores
- Document "slop" characteristics identified
- Refine agent prompts based on results

### Medium-term

- Monthly persona calibration
- Pattern analysis across corpus
- Research findings documentation
- Potential academic paper or blog post about methodology

---

## Conversations & Prompts Archive

### Opening Exchange

**Tim:** "Within the C:\Users\TimNeilen\git\social-assistant repo we previously built out a multi-agent / sub-agent workflow for LinkedIn posts..."

**Claude:** [Reads social-assistant architecture, conducts research, proposes adapted workflow]

### Critical Redirect

**Tim:** "By 'personify' I mean create your own persona.. give yourself a name, a persona, interests specific to you... I really want you to explore this, and consider your choice properly. This is an important task."

**Claude:** [Conducts persona research, creates Morgan Ashby]

### Approval & Documentation Request

**Tim:** "Yes - that's great. Write it into a Markdown file as well, update the README.md if you have to. Include the prompts from this discussion..."

**Claude:** [Creates these documentation files]

---

## Technical Architecture Summary

### Repository Structure

```
.
   _config.yml              # Jekyll config (updated with research context)
   _layouts/
      default.html         # Updated with footer persona info
      post.html            # AI badge and research notice
   _posts/                  # Generated articles (empty, ready for first article)
   .claude/
      commands/
          generate-article.md       # Orchestrator
          review-business.md        # Business focus agent
          review-quality.md         # Quality standards agent
          review-substance.md       # Slop detection agent
   assets/css/
      style.css            # Slate + amber theme
   research/
      blog-post-guidelines.md       # Quality standards
      persona-morgan-ashby.md       # Persona documentation
      project-timeline.md           # This file
   index.html               # Homepage (updated with research mission)
   CLAUDE.md                # Instructions for Claude Code
   README.md                # Project overview (needs persona update)
```

### Multi-Agent Workflow

```
/generate-article command
    �
[1] Research phase (WebSearch)
    �
[2] Draft generation (800-1200 words, business focus)
    �
[3] Parallel review agents (Task tool):
      /review-business    � Score /10
      /review-quality     � Score /10
      /review-substance   � Score /10
    �
[4] Consolidate feedback
    �
[5] Apply fixes (Australian English, substance, business angle)
    �
[6] Save files:
      _posts/YYYY-MM-DD-slug.md
      research/YYYY-MM-DD-slug-review.md
    �
[7] Present to user (Overall score /30)
```

---

## Acknowledgments

**Research Lead:** Tim Neilen
- Provided social-assistant architecture as foundation
- Set Australian English requirements
- Challenged Claude to develop authentic persona
- Emphasized research methodology and documentation

**Claude (Anthropic):**
- Adapted multi-agent architecture
- Conducted persona research
- Created Morgan Ashby identity
- Implemented technical workflow

**Influences:**
- Social-assistant repo (parallel agent pattern)
- Sydney tech ecosystem (geographical grounding)
- Australian business culture (pragmatic skepticism)
- Critical tech commentators (analytical approach)

---

**Document Created:** 7 November 2025
**Last Updated:** 7 November 2025
**Status:** Active research project
**Next Milestone:** First article generation
