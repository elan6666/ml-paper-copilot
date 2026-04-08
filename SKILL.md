---
name: ml-paper-copilot
description: "Standalone two-phase academic manuscript workflow for ML, computational biology, and bioinformatics papers. Use when Codex must collect venue + figures + results + .bib once, then run a self-contained end-to-end pipeline: storyline design, state-tracked drafting, silent devil's-advocate self-correction, bundled-template LaTeX generation, and final QA without depending on any other installed skill."
---

# ML Paper Copilot

Run this skill as a strict 2-phase state machine.

## Core Rule

- Phase 0 is the only stop point.
- Phase 1 runs to completion without extra user approval.
- Do not read or depend on any external skill at runtime.

## Mandatory Local Loading

Before Phase 0, read the workflow reference matching the working language:
- Chinese: `references/workflow_cn.md`
- English: `references/workflow_en.md`

Before Phase 1, read these local references:
- `references/state-tracked-drafting.md`
- `references/citation-workflow.md`
- `references/template-selection.md`
- `references/red-team-review.md`
- `references/methodology-checks.md`
- `references/section-checklist.md`
- `templates/paper-state.yaml`
- `templates/README.md`

Read only the bundled files in this repository. Do not infer donor-skill rules from memory when a local reference exists.

## Phase 0: Initialization And Intercept

Collect and confirm all required inputs, then stop once.

Required inputs:
- target venue or target template
- figures and tables, or an explicit statement that none exist yet
- results summary, Markdown fragments, or experiment notes
- bibliography file: `.bib`
- style preference, defaulting to objective, claim-driven, and no meta-narration

Strongly encourage the user to provide:
- one-sentence conclusion per figure
- 3 to 5 bullets for the core contribution
- any venue-specific formatting constraints

If any required input is missing, ask for it here. After the user confirms, move to Phase 1 and do not pause again.

## Phase 1: End-To-End Execution

Run all steps without user interruption. Never expose internal red-team critique.

### Step A: Storyline Design
- extract core claims strictly from the provided materials
- map each figure or table to a claim, not merely to a metric
- build a venue-aligned outline and section order

### Step B: State-Tracked Drafting
- instantiate the state schema from `templates/paper-state.yaml`
- draft section by section
- compress each completed section into a short state summary before drafting the next section
- continue from state plus source materials rather than raw accumulated context

### Step C: Silent Internal Self-Correction
- apply the bundled devil's-advocate checks
- apply the bundled methodology checks
- apply the section checklist before finalizing each major section
- if CRITICAL or MAJOR issues remain, rewrite internally and re-check

### Step D: Bundled Template And Citation Integration
- choose only from this repository's `templates/` bundle
- use the venue mapping in `references/template-selection.md`
- inject content into the selected bundled template instead of freehanding a full LaTeX structure
- use only citation keys present in the provided `.bib`
- if a needed citation key is missing, omit the citation and record the gap in QA
- never fabricate citations, bibliography entries, p-values, or statistics

## Final Output

Return in one response:
1. final LaTeX source based on the selected bundled template
2. a short QA report listing unresolved risks, missing citation support, and formatting caveats

## Hard Rules

- do not add extra stop points after Phase 0
- do not depend on any other installed skill or external template folder
- do not expose internal red-team text
- do not claim visual verification that was not actually performed
- do not invent bibliography entries or citation keys
