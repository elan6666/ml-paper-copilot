---
name: ml-bio-paper-standardizer
description: Standardize, polish, and structurally revise computational biology and machine learning papers, especially single-cell perturbation, benchmarking, and method papers. Use when rewriting abstract/introduction/methods/results/discussion, enforcing result story chains, improving figure captions, deciding equation-numbering scope, setting citation-style policy, or aligning notebooks and figures to the paper narrative.
---

# ML-Bio Paper Standardizer

Use this skill for Chinese or bilingual method papers in computational biology, bioinformatics, and ML-for-biology. It is especially suitable for papers on:

- single-cell perturbation prediction
- single-cell foundation/fine-tuned models
- benchmark-heavy biology ML papers
- reference-conditioned / generative / representation-learning method papers
- manuscripts targeting venues such as Nature Biotechnology, Nature Computational Science, Bioinformatics, or IEEE/ACM TCBB

It is less suitable for:

- pure theory papers with little experimental narrative
- wet-lab-only biology papers
- clinical trial or epidemiology manuscripts

## Workflow

1. Read the current manuscript or section draft.
2. If the repo contains a project-specific standards file, read it first. For TriShift, prefer:
   - `docs/md/trishift_paper_standards_cn.md`
3. Then read the default standard from this skill:
   - Chinese: `references/paper_standards_cn.md`
   - English: `references/paper_standards_en.md`
4. Apply revisions in this order:
   - fix story chain and section responsibilities
   - remove meta-commentary and advisor-facing narration
   - separate mathematical formulation from implementation details
   - rewrite Results as claim-driven subsections, not metric lists
   - make figure captions self-contained
   - number only core equations that will be referenced later
   - keep citation style venue-dependent; do not force Nature-style superscripts unless the venue is fixed
   - raise Discussion to biological meaning without overclaiming
5. If the manuscript is figure-driven, enforce a stable figure-to-story mapping. For single-cell perturbation method papers, the default is:
   - Fig. 1: task framing + architecture + dataset scope
   - Fig. 2: standard benchmark
   - Fig. 3: mechanism / systematic-variation analysis
   - Fig. 4: hard generalization
   - Fig. 5: biology / pathway recovery
6. When generating final docs, visually check PDF/DOCX pages and fix layout regressions.

## Hard Rules

- Do not write Results like a metric directory.
- Do not explain why you arranged the paper in a certain way.
- Do not mix code flags and config names into the main mathematical narrative.
- Do not invent error bars, sample sizes, statistical tests, or p-values that are not actually present.
- Do not number every displayed formula. Number only equations that are referenced or central to the paper's logic.
- Do not hard-switch citation style before the target venue is fixed.

## Expected Output

When this skill is used well, the manuscript should end up with:

- a clear, claim-driven story chain
- concise and journal-ready subsection titles
- self-contained figure captions
- a clean Methods section with math-first exposition
- a Discussion section that states biological meaning, limitations, and future directions
- stable alignment between notebook outputs, figures, and text
