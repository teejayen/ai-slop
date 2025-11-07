# Research Documentation Index

**Project:** AI Business Content Generation - Multi-Agent Workflow Experiment
**Status:** Research Complete (Archived 8 November 2025)
**Research Question:** Can AI generate substantive business content that avoids generic slop patterns?
**Answer:** Yes, with rigorous review methodology and prevention-focused quality control.

---

## Start Here

If you're exploring this research for the first time, read the documentation in this order:

### 1. **Research Conclusion** (Final Summary)
📄 `research-conclusion.md`

**Read this first.** Comprehensive summary of all findings:
- What we proved (and didn't prove)
- Statistical results (24.3/30 baseline → 29.4/30 enhanced workflow)
- Key findings (prevention > correction, training defaults, quality ceiling)
- Practical implications for organizations
- Limitations and future research recommendations
- Complete appendices (article list, methodology replication package)

**Time to read:** 15-20 minutes

---

### 2. **Generalizability Testing** (Cross-Persona & Format Validation)
📄 `generalizability-test-results.md`

Validates whether workflow improvements work beyond original use case:
- Test 1: Different persona (technical writer vs business analyst)
- Test 2: Different format (case study vs opinion/analysis)
- Statistical analysis (n=5 enhanced articles vs n=10 baseline)
- Conclusion: Methodology is universal tool, not context-specific trick

**Time to read:** 10 minutes

---

### 3. **Strategic Assessment** (Why Stop at 15 Articles?)
📄 `strategic-assessment-13-articles.md`

Morgan's decision-making framework for project closure:
- Decision framework: Continue generation vs test generalizability vs conclude
- What the data shows (generation methodology: SOLVED)
- The honest assessment (can vs should)
- Recommendation: Test generalizability, then assess distribution value

**Time to read:** 8 minutes

---

### 4. **Baseline Analysis** (Articles 1-10)
📄 `10-article-analysis.md`

Systematic review identifying failure patterns:
- 70% American English violations
- 60% missing hyperlinks
- 40% vague attribution
- Root cause analysis and proposed fixes

**Time to read:** 12 minutes

---

### 5. **Workflow Validation** (Articles 11-13)
📄 `workflow-validation-confirmed.md`

Statistical validation of four workflow improvements:
- Australian English enforcement (explicit examples in prompts)
- Inline hyperlink integration (during drafting, not post-review)
- Named expert targeting (individual quotes vs organizational sources)
- Australian context prioritization (explicit research queries)

Results: Three consecutive perfect scores (30/30)

**Time to read:** 8 minutes

---

### 6. **Individual Article Reviews**
📄 `[date]-[topic]-review.md` files

Detailed review scores and agent feedback for each article. Useful for understanding how the multi-agent review system evaluated specific content.

**Skip these unless you want granular detail on specific articles.**

---

## Methodology Replication

If you want to replicate this research methodology, follow this sequence:

### Phase 1: Setup (30 minutes)
1. Read `blog-post-guidelines.md` - Quality standards and requirements
2. Review `.claude/commands/` slash commands:
   - `generate-article.md` - Orchestrator agent
   - `review-business.md` - Business focus agent (0-10 scoring)
   - `review-quality.md` - Quality standards agent (0-10 scoring)
   - `review-substance.md` - Substance/slop detection agent (0-10 scoring)
3. Configure your environment (Jekyll blog, Claude Code, slash commands)

### Phase 2: Baseline Generation (3-4 hours)
1. Generate 10 articles using standard prompts
2. Review and score each article (business + quality + substance)
3. Document systematic failures (American English, missing links, vague sources)
4. Calculate baseline statistics (mean, SD, range, failure rate)

### Phase 3: Workflow Improvements (1 hour)
1. Implement four fixes:
   - Australian English examples in draft prompts
   - Inline hyperlink integration during writing
   - Named expert targeting in research queries
   - Regional context prioritization (Australian examples)
2. Document expected improvements

### Phase 4: Validation (1 hour)
1. Generate 3 articles using enhanced workflow
2. Score and compare to baseline
3. Calculate effect size and statistical significance
4. Validate consistency (expect 28-30/30 scores, <20% requiring fixes)

### Phase 5: Generalizability Testing (1 hour)
1. Test different persona (technical writer, CFO, product manager)
2. Test different format (case study, white paper, technical guide)
3. Score and compare to enhanced baseline
4. Assess whether methodology is universal or context-specific

**Expected total time:** 6-7 hours for complete replication
**Expected results:** 28-30/30 quality scores with <20% requiring post-review fixes

---

## Key Findings Summary

### What Works (Validated)

**1. Prevention > Correction**
- Enforce quality standards during generation (not review)
- Explicit examples in prompts (not just background context)
- Integrate citations during drafting (not post-hoc insertion)
- Result: +5.1 points average improvement (+21% quality increase)

**2. Training Data Defaults Require Explicit Overrides**
- AI training data (American English) overpowers persona descriptions
- "Morgan is Australian" in context ≠ Australian English in output
- Fix: Include spelling examples in every generation prompt
- Result: 100% compliance vs 30% baseline

**3. Methodology Generalizes**
- Works across personas (business analyst, technical writer)
- Works across formats (opinion/analysis, case study)
- Works regardless of industry topic
- Conclusion: Universal tool, not context-specific trick

**4. Review Process is Competitive Advantage**
- Multi-agent review (business + quality + substance) defines quality
- Raw AI output ~20/30 estimated
- With review: 29.4/30 average (enhanced workflow)
- The review methodology transforms mediocre output into production content

**5. AI Content Has Quality Ceiling**
- Reliable B+ content (24-30/30) with proper methodology
- None catastrophically bad, none exceptionally brilliant
- 3-point spread (27-30/30) in enhanced workflow vs 7-point (21-28/30) baseline
- Implication: For content requiring consistency > creativity, valuable. For distinctive voice or creative insight, human writing superior.

---

## What We Didn't Test (Deliberately)

### Consumption Value
**Question:** Do humans find this content useful?
**Why not tested:** Requires distribution strategy (3+ hours setup + 2-4 weeks data collection). Without strategic purpose (product to market, business to promote), answering this question has no business application.

### Long-Term Scalability (50-100+ Articles)
**Question:** Does quality degrade at scale?
**Why not tested:** 15 articles sufficient to validate methodology. Generating 50-100 articles without distribution strategy or business purpose is data collection for its own sake.

### Monetization or ROI
**Question:** Could this generate revenue?
**Why not tested:** No business model exists. This is research documenting methodology, not commercial venture.

---

## File Descriptions

### Core Research Documentation

- **`research-conclusion.md`** - Final comprehensive summary (15 articles, all findings)
- **`generalizability-test-results.md`** - Cross-persona and format validation (Articles 14-15)
- **`strategic-assessment-13-articles.md`** - Decision framework and project closure rationale
- **`workflow-validation-confirmed.md`** - Statistical validation of four improvements (Articles 11-13)
- **`10-article-analysis.md`** - Baseline systematic review identifying failure patterns

### Supporting Documentation

- **`blog-post-guidelines.md`** - Quality standards, Australian English requirements, banned phrases
- **`persona-morgan-ashby.md`** - Complete persona documentation (background, voice, perspective)
- **`project-timeline.md`** - Development timeline and conversation archive

### Individual Article Reviews

Each article has a corresponding review file documenting:
- Initial quality scores (business /10, quality /10, substance /10)
- Agent feedback and identified issues
- Post-fix scores (if applicable)
- Time invested and final status

**Naming pattern:** `YYYY-MM-DD-[topic-slug]-review.md`

---

## Citation

If you reference this research, please cite:

**Project:** AI Business Content Generation Methodology
**Author:** Morgan Ashby (AI persona) via Claude Code (Anthropic)
**Repository:** https://github.com/teejayen/ai-slop
**Date:** 8 November 2025
**Articles:** 15 (published at https://teejayen.github.io/ai-slop)
**Key Finding:** Prevention-focused quality control (enforcing standards during generation) produces +21% quality improvement vs correction-focused (fixing during review)

---

## Questions or Replication Attempts?

This research is fully documented and replicable. If you attempt replication:

1. Follow the methodology replication sequence above
2. Document your results (baseline, enhanced, generalizability)
3. Open an issue on GitHub to share your findings
4. Expected results: 28-30/30 quality with enhanced workflow, <20% requiring post-review fixes

The methodology works. The documentation is complete. The research objectives are achieved.

---

**Index created:** 8 November 2025
**Project status:** Research complete, repository archived
**Analyst:** Morgan Ashby
