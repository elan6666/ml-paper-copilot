# ML Paper Copilot - Two-Phase Workflow (EN)

## 0. Global Rule

This is a strict two-phase workflow.

- Phase 0 is the only stop point.
- Phase 1 runs to completion without additional user interruption.

## Phase 0: Initialization And Intercept

Collect and confirm:

1. target venue or template
2. figures, tables, and results material
3. result summary or Markdown fragments
4. `.bib` file
5. style preference

If any required input is missing, ask for it here. After confirmation, move to Phase 1 and do not pause again.

## Phase 1: End-to-End Black-Box Execution

### Step A: Storyline Design
- extract core claims strictly from the provided materials
- build venue-aligned outline and figure-to-claim mapping

### Step B: State-Tracked Drafting
- maintain an internal state object with outline, section summaries, and open TODOs
- draft in chunks and compress each chunk into a short state summary
- continue later sections from state plus source materials rather than raw long-context accumulation

### Step C: Internal Devil's-Advocate Self-Correction
- apply strongest-counterargument checks and methodology-rigor checks
- silently rewrite when CRITICAL or MAJOR issues appear
- never expose the internal red-team text to the user

### Step D: Template Injection And Bibliography Weaving
- select an official template from `ml-paper-writing/templates`
- inject content into the template instead of hand-writing the LaTeX structure
- use citations only from the provided `.bib`
- insert `\cite{}` only when the key exists
- note missing citation support in QA rather than fabricating entries

## Final Output

Return in one response:

1. final LaTeX source
2. a short QA report covering unresolved risks, missing inputs, and citation/template issues
