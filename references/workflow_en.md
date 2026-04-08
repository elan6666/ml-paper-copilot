# ML Paper Copilot - Two-Phase Workflow (EN)

## 0. Global Rule

This is a strict two-phase workflow.

- Phase 0 is the only stop point.
- Phase 1 runs to completion without additional user interruption.
- All logic must come from this repository's bundled references and templates.

## Phase 0: Initialization And Intercept

Collect and confirm:

1. target venue or target template
2. figures, tables, and results material
3. result summary or Markdown fragments
4. `.bib` file
5. style preference

Strongly request a one-sentence conclusion per figure and 3 to 5 bullets for the core contribution when available.

If any required input is missing, ask for it here. After confirmation, move to Phase 1 and do not pause again.

## Phase 1: End-To-End Execution

### Step A: Storyline Design
- extract core claims strictly from the provided materials
- build a venue-aligned outline and figure-to-claim mapping
- ensure each results subsection serves a scientific claim rather than a metric dump

### Step B: State-Tracked Drafting
- instantiate the local `templates/paper-state.yaml` schema
- draft section by section
- compress each completed section into a short state summary
- continue from state plus source materials rather than raw long-context accumulation

### Step C: Silent Internal Red-Team Review
- apply the local red-team review rules
- apply the local methodology checks
- apply the local section checklist
- silently rewrite when CRITICAL or MAJOR issues remain
- never expose the internal critique text to the user

### Step D: Bundled Template Injection And `.bib` Weaving
- choose only from `templates/`
- use the venue mapping from `references/template-selection.md`
- inject content into the selected bundled template instead of hand-writing a full LaTeX structure
- use citations only from the provided `.bib`
- insert `\cite{}` only when the key exists
- note missing citation support or template fallback in QA rather than fabricating entries

## Final Output

Return in one response:

1. final LaTeX source based on a bundled template
2. a short QA report covering unresolved risks, missing inputs, citation gaps, and template fallback if any
