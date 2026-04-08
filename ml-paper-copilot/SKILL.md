---
name: ml-paper-copilot
description: Two-phase, approval-gated, fully automated academic manuscript workflow for ML, computational biology, and bioinformatics papers. Use when Codex must collect venue + figures + results + .bib once, then run a single end-to-end pipeline: storyline design, state-tracked drafting, internal devil's-advocate self-correction, template-based LaTeX typesetting, and final QA.
---

# ML Paper Copilot (2-Phase Auto Workflow)

Use this skill when the user wants a minimal, anti-fragile, two-phase pipeline that only pauses once for confirmation, then runs end-to-end without interruptions.

## Core Operating Rule (Strict 2-Phase State Machine)

- Phase 0 is the ONLY stop point.
- Phase 1 runs to completion without user interaction.
- Do not add extra approval gates beyond Phase 0.

## Mandatory Knowledge Loading (Before Phase 0)

You MUST explicitly read the following local references before starting Phase 0:

1. Red-team self-correction:
   - `C:\Users\16523\.agents\skills\academic-paper-reviewer\agents\devils_advocate_reviewer_agent.md`
   - `C:\Users\16523\.agents\skills\academic-paper-reviewer\agents\methodology_reviewer_agent.md`
   - `C:\Users\16523\.agents\skills\paper-self-review\SKILL.md`
2. Template injection + citation automation:
   - `C:\Users\16523\.codex\skills\ml-paper-writing\references\citation-workflow.md`
   - `C:\Users\16523\.codex\skills\ml-paper-writing\templates\README.md`
3. State-tracked drafting:
   - `C:\Users\16523\.codex\skills\autoresearch\references\agent-continuity.md`
   - `C:\Users\16523\.codex\skills\autoresearch\templates\research-state.yaml`

Also read the workflow reference for the working language:
- Chinese: `references/workflow_cn.md`
- English: `references/workflow_en.md`

Do not infer rules from memory when these files are available.

## Phase 0 (Initialization And Intercept)

Collect and confirm all inputs. Stop and wait once.

Required inputs:
- target venue or template (ICLR/NeurIPS/ICML/ACL/AAAI/etc.)
- figures and tables (or explicit statement that none exist yet)
- results summary or Markdown fragments
- bibliography file: `.bib`
- style preference (objective, claim-driven, no meta-narration by default)

If any required input is missing, ask for it. After confirmation, proceed to Phase 1 and do not pause again.

## Phase 1 (End-to-End Black-Box Execution)

Run these steps without user interruption. Do not show internal red-team outputs.

A. Storyline Design
- Extract core claims strictly from provided materials.
- Build venue-aligned outline and figure-to-claim mapping.

B. State-Tracked Drafting (Anti-Context-Loss)
- Create an internal state object (outline, section summaries, open TODOs).
- Draft in sections, then compress each section into a 5-10 line state summary.
- Use the state summaries to continue drafting subsequent sections.

C. Internal Devil's-Advocate Self-Correction (Silent)
- Apply strongest counter-argument checks and methodology rigor checks.
- If CRITICAL/MAJOR issues are found, revise internally and re-check.
- Do NOT expose the red-team critique to the user.

D. Template-First Typesetting + Auto-Bibliography
- Select the official template from `ml-paper-writing/templates` matching the venue.
- Inject content into the template instead of hand-writing LaTeX structure.
- Use `.bib` entries only; do not fabricate citations.
- Insert `\cite{}` only when the entry exists in the provided `.bib`.
- If a needed citation is missing, omit it and note in QA.

## Final Output

Output in one response:
1. Final LaTeX source that compiles with the chosen template
2. A short QA report listing any unresolved risks or missing inputs

## Hard Rules

- Do not add any extra stop points after Phase 0.
- Do not invent citations, p-values, or statistics.
- Do not generate LaTeX templates from memory if a template exists.
- Do not expose internal red-team text.
