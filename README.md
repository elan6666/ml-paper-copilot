# ml-paper-copilot

`ml-paper-copilot` is a standalone Codex skill for turning figures, experiment results, Markdown fragments, and `.bib` libraries into a two-phase automated manuscript workflow for machine learning, computational biology, and bioinformatics papers.

The repository is self-contained. It does not depend on any other installed skill at runtime. All drafting logic, review rules, citation policy, state-tracking guidance, and LaTeX templates live inside this repository.

## Highlights

- Two-phase state-machine workflow
- Exactly one approval stop before full execution
- Self-contained references and bundled venue templates
- State-tracked drafting to reduce long-context fragility
- Silent devil's-advocate and methodology self-review before output
- `.bib`-only citation policy with no fabricated references
- Final QA covering evidence gaps, citation gaps, and template fallback

## Workflow

The skill runs in two phases:

1. Phase 0: initialization and intercept
2. Phase 1: fully automated end-to-end execution

Hard constraint: the agent stops once after Phase 0, then completes Phase 1 without additional approval gates.

## Input Materials

Phase 0 works best when the user provides structured material instead of only broad requests.

Recommended inputs:

- target venue or template
- figures or tables
- a one-sentence conclusion for each figure
- three to five bullet points describing the core contribution
- result summaries or metric notes
- Markdown fragments from an existing draft
- a `.bib` file
- any formatting constraints that matter to the target venue

## Bundled Assets

This repository contains its own operating references and drafting templates:

- `references/red-team-review.md`
- `references/methodology-checks.md`
- `references/section-checklist.md`
- `references/citation-workflow.md`
- `references/state-tracked-drafting.md`
- `references/template-selection.md`
- `templates/paper-state.yaml`
- `templates/iclr/`, `templates/neurips/`, `templates/icml/`, `templates/acl/`, `templates/aaai/`

The bundled templates are venue-compatible house templates intended for self-contained drafting. If an official kit is provided later, the manuscript can be adapted into it without changing the scientific content.

## Repository Structure

```text
ml-paper-copilot/
|-- README.md
|-- LICENSE
|-- .gitignore
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- references/
|   |-- workflow_cn.md
|   |-- workflow_en.md
|   |-- red-team-review.md
|   |-- methodology-checks.md
|   |-- section-checklist.md
|   |-- citation-workflow.md
|   |-- state-tracked-drafting.md
|   `-- template-selection.md
`-- templates/
    |-- README.md
    |-- paper-state.yaml
    |-- iclr/
    |-- neurips/
    |-- icml/
    |-- acl/
    `-- aaai/
```

## Installation

Place the repository root under your Codex skills directory, or install directly from GitHub with the Skills CLI.

- Windows: `%USERPROFILE%\.codex\skills\`
- Cross-platform: `${CODEX_HOME}/skills/`

Direct install:

```text
npx skills add https://github.com/elan6666/ml-paper-copilot -g -y
```

## Example Invocation

```text
Use $ml-paper-copilot to collect my venue, figures, results, and .bib in Phase 0, then run a self-contained end-to-end paper workflow in Phase 1.
```

## Interaction Example

```text
User: Use $ml-paper-copilot. I attached 3 figure images, a results.md draft, and references.bib.
Agent: Phase 0. What is the target venue? Please also provide a one-sentence conclusion for each figure and 3 bullet points for the core contribution.
User: Target venue is ICLR. Here are the figure conclusions and contribution bullets.
User: Approved. Continue.
Agent: Phase 1. I will now run storyline design, state-tracked drafting, internal self-review, bundled-template assembly, and final QA, then return the final LaTeX source and QA report.
```

## Design Principles

- Treat the paper as a scientific argument, not a sequence of metrics.
- Map every figure and table to a claim.
- Keep methods mathematically structured and implementation details separate.
- Do not invent statistics, p-values, sample sizes, or error-bar definitions.
- Do not generate citations outside the provided `.bib`.
- Do not rely on any external skill or template directory at runtime.

## Output Expectations

When used correctly, the skill should produce:

- a venue-adapted paper plan
- state-tracked section drafting
- a final LaTeX manuscript using a bundled template
- citation usage constrained by the provided `.bib`
- a short QA report

## License

This repository is released under the MIT License.
