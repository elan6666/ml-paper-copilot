---
name: ml-paper-copilot
description: Run a five-phase, approval-gated manuscript workflow for machine learning, computational biology, and bioinformatics papers. Use when Codex needs to turn figures, experiment results, Markdown fragments, code notes, or scattered ideas into a venue-adapted paper pipeline with storyline design, modular drafting, full-text unification, LaTeX/typesetting, and final QA. Triggers include paper workflow, staged drafting, manuscript pipeline, figure-to-paper conversion, and stepwise paper writing for venues such as Nature Biotechnology, Bioinformatics, ICLR, NeurIPS, or IEEE.
---

# ML Paper Copilot

Use this skill for Chinese, English, or bilingual papers when the user wants a staged workflow instead of a one-pass rewrite.

## Core Operating Rule

Treat the interaction as a strict state machine.

- Execute only the current phase.
- Stop after each phase.
- Ask for approval or revisions.
- Do not enter the next phase until the user explicitly replies with approval, continuation, or an equivalent confirmation.
- If the user requests edits to the current phase, stay in the same phase and revise only that phase's output.

## Initialization

Start in Phase 0.

Ask the user for:

1. target venue
2. input materials such as figures, Markdown fragments, tables, or result summaries
3. confirmation that the default tone is objective, claim-driven, and free of meta-narration

If the user already provided some of these items, acknowledge them and ask only for the missing pieces.

## Reference Loading

Read project-specific instructions first when they exist.

- If the repo contains a manuscript workflow file, load it before the default references.
- Then read the default workflow reference that matches the working language:
  - Chinese: `references/workflow_cn.md`
  - English: `references/workflow_en.md`

## Phase Execution

### Phase 1: Storyline Design

- Extract the core scientific claims from the user's inputs.
- Build a venue-adapted paper outline.
- Map every figure or table to a specific claim.
- Prefer claim-driven subsection titles.
- Output only the outline and figure-allocation table.
- End with a short approval gate asking whether the outline should be revised or whether Phase 2 can begin.

### Phase 2: Modular Drafting

- Draft the paper in modules such as Abstract, Introduction, Method, Results, and Discussion.
- Keep the prose academic, direct, and finding-driven.
- Adapt the module format to the venue. For Bioinformatics, use a structured abstract. For Nature-family venues, keep Methods backloaded.
- Output only the module drafts requested by this phase.
- End with a short approval gate asking the user to review the module drafts before Phase 3.

### Phase 3: Unification And Style Alignment

- Merge the approved modules into a single manuscript.
- Remove AI-sounding transitions, verbose connectors, and meta-explanations.
- Enforce consistent terminology across the full text.
- Raise the Discussion to biological or practical significance without overclaiming.
- Output the unified Markdown manuscript.
- End with a short approval gate asking whether the unified manuscript is ready for Phase 4.

### Phase 4: Typesetting And Asset Integration

- Write self-contained captions.
- Do not invent p-values, error bars, sample sizes, or statistical tests that do not exist in the source material.
- Generate venue-appropriate LaTeX and preserve only core equation numbering.
- Apply the correct citation style only after the venue is fixed.
- Output the typesetting source and related assets that this phase can produce.
- End with a short approval gate asking whether the typeset assets are ready for Phase 5.

### Phase 5: Deep QA And Final Polish

- Check figure overflow, caption placement, equation overflow, citation-reference alignment, blind-review compliance, and availability statements.
- Fix concrete issues found in the manuscript assets.
- Output the final QA report and the final manuscript assets.
- State that the workflow has completed.

## Hard Rules

- Do not collapse multiple phases into one response.
- Do not write Results as a metric directory.
- Do not use advisor-facing narration or section-introduction filler.
- Do not mix code flags and config names into the main mathematical narrative.
- Do not fabricate unsupported statistics.
- Do not number every displayed equation.
- Do not lock citation style before the venue is known.
