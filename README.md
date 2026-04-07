# ml-paper-copilot

`ml-paper-copilot` is a reusable Codex skill for turning figures, experiment results, Markdown fragments, and scattered notes into a staged manuscript workflow for machine learning, computational biology, and bioinformatics papers.

Unlike a one-shot paper rewriter, this skill operates as an approval-gated workflow engine. It plans the paper first, drafts in phases, unifies the manuscript, generates typesetting assets, and stops after each phase for user review.

## Highlights

- Five-phase state-machine workflow
- Explicit stop points between phases
- Venue-aware structure for Nature-family venues, Bioinformatics, ICLR, NeurIPS, and IEEE-style papers
- Claim-driven paper construction instead of metric-dump writing
- Caption and LaTeX generation only after narrative approval
- Final QA for figures, equations, citations, blind review, and availability statements

## Workflow

The skill runs in five gated phases:

1. Initialization and configuration confirmation
2. Storyline design and outline building
3. Modular drafting
4. Full-text unification and style alignment
5. Typesetting and deep QA

Hard constraint: the agent must stop after each phase and wait for explicit user approval before continuing.

## Typical Uses

- Turn benchmark results and figures into a paper-ready storyline
- Build a manuscript step by step instead of requesting a full rewrite at once
- Adapt section order and abstract format to a target venue
- Produce self-contained captions and LaTeX after the paper logic is approved
- Run a final pre-submission QA pass on the manuscript assets

## Repository Structure

```text
ml-paper-copilot/
|-- README.md
|-- LICENSE
|-- .gitignore
`-- ml-paper-copilot/
    |-- SKILL.md
    |-- agents/
    |   `-- openai.yaml
    `-- references/
        |-- workflow_cn.md
        `-- workflow_en.md
```

## Installation

Place the `ml-paper-copilot` folder under your Codex skills directory.

- Windows: `%USERPROFILE%\.codex\skills\`
- Cross-platform: `${CODEX_HOME}/skills/`

After installation, invoke the skill by name in a paper-writing task.

## Example Invocation

```text
Use $ml-paper-copilot to turn my figures, notes, and results into a five-phase paper workflow. Stop after each phase and wait for my approval before continuing.
```

## Design Principles

- Treat the paper as a scientific argument, not a sequence of metrics.
- Map every figure and table to a claim.
- Keep Methods mathematically structured and implementation details separate.
- Do not invent statistics, p-values, sample sizes, or error-bar definitions.
- Do not lock citation style before the target venue is fixed.
- Keep Discussion ambitious enough to matter and restrained enough to stay defensible.

## Output Expectations

When used correctly, the skill should produce:

- a venue-adapted outline
- a claim-to-figure mapping
- module drafts for major sections
- a unified manuscript with cleaner academic style
- typesetting assets such as Markdown and LaTeX
- a final QA report

## License

This repository is released under the MIT License.
