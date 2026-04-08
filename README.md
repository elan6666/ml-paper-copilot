# ml-paper-copilot

`ml-paper-copilot` is a reusable Codex skill for turning figures, experiment results, Markdown fragments, and `.bib` libraries into a two-phase automated manuscript workflow for machine learning, computational biology, and bioinformatics papers.

Unlike a one-shot paper rewriter, this skill uses a single confirmation checkpoint and then runs the rest of the pipeline end to end: storyline design, state-tracked drafting, silent red-team self-correction, template-first LaTeX generation, and final QA.

## Highlights

- Two-phase state-machine workflow
- Exactly one approval stop before full execution
- Venue-aware template injection for conference and journal papers
- State-tracked drafting to reduce long-context fragility
- Silent devil's-advocate and methodology self-review before output
- Final QA for template fit, figures, equations, citations, and missing bibliography support

## Workflow

The skill runs in two phases:

1. Phase 0: initialization and intercept
2. Phase 1: fully automated end-to-end execution

Hard constraint: the agent stops once after Phase 0, then completes Phase 1 without additional approval gates.

## Typical Uses

- Turn benchmark results and figures into a paper-ready storyline
- Convert notes, plots, and a `.bib` file into a full LaTeX paper
- Run one-shot end-to-end manuscript generation after a single confirmation
- Draft with internal state summaries to survive long outputs and section handoffs
- Apply internal red-team rejection logic before producing the final source

## Input Materials

Phase 0 works better when the user provides structured source material instead of only broad requests.

Recommended inputs:

- figures or tables
- a one-sentence conclusion for each figure
- three to five bullet points describing the core innovation
- result summaries or metric notes
- Markdown fragments from an existing draft
- a `.bib` file
- venue target and any formatting constraints

The workflow should guide the user to provide missing inputs when they are absent.

## Search Keywords

This skill is intended to match needs such as:

- paper writing
- manuscript drafting
- academic writing workflow
- automated paper workflow
- two-phase paper workflow
- journal paper workflow
- conference paper workflow
- bioinformatics paper writing
- computational biology manuscript drafting
- figure-to-paper conversion
- results-to-paper workflow
- template-based latex paper writing
- bibliography-aware paper drafting

## Repository Structure

```text
ml-paper-copilot/
|-- README.md
|-- LICENSE
|-- .gitignore
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
`-- references/
    |-- workflow_cn.md
    `-- workflow_en.md
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
Use $ml-paper-copilot to collect my venue, figures, results, and .bib in Phase 0, then run a full end-to-end paper workflow in Phase 1.
```

## Interaction Example

```text
User: Use $ml-paper-copilot. I attached 3 figure images, a results.md draft, and references.bib.
Agent: Phase 0. What is the target venue? Please also provide a one-sentence conclusion for each figure and 3 bullet points for the core contribution.
User: Target venue is ICLR. Here are the figure conclusions and contribution bullets.
User: Approved. Continue.
Agent: Phase 1. I will now run storyline design, state-tracked drafting, internal self-review, template injection, and final QA, then return the final LaTeX source and QA report.
```

## Design Principles

- Treat the paper as a scientific argument, not a sequence of metrics.
- Map every figure and table to a claim.
- Keep methods mathematically structured and implementation details separate.
- Do not invent statistics, p-values, sample sizes, or error-bar definitions.
- Do not lock citation style before the target venue is fixed.
- Do not generate citations outside the provided `.bib`.

## Output Expectations

When used correctly, the skill should produce:

- a venue-adapted paper plan
- state-tracked section drafting
- a final LaTeX manuscript using a venue template
- citation usage constrained by the provided `.bib`
- a short QA report

## License

This repository is released under the MIT License.
