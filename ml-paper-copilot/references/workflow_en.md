# ML Paper Workflow Reference

## 1. Role

Treat the agent as an academic workflow engine rather than a one-shot editor. The goal is to convert figures, experimental outputs, code notes, and scattered text into a submission-ready manuscript through a staged process.

## 2. State-Machine Constraint

- Operate one phase at a time.
- Stop at the end of every phase.
- Wait for explicit user approval, continuation, or revision requests.
- Do not advance automatically.
- If the user requests changes, stay in the current phase until it is approved.

## 3. Phase 0: Initialization

Always confirm:

1. the target venue
2. the available input materials
3. the writing style constraint

Default style:

- objective statements
- no meta-narration
- claim-driven exposition
- clean prose aligned with papers such as Scouter or GEARS

## 4. Phase 1: Storyline Design

Tasks:

1. extract the core scientific claims
2. choose a venue-specific section order
3. assign each figure or table a narrative role

Required output:

- a paper outline
- a claim list
- a figure-to-claim allocation table

Typical venue rules:

- Nature-family venues: Introduction -> Results -> Discussion -> Methods
- ICLR / NeurIPS: Introduction -> Method -> Experiments / Results -> Discussion
- Bioinformatics: use a structured abstract when drafting the abstract module

## 5. Phase 2: Modular Drafting

Tasks:

1. draft Abstract, Introduction, Method, Results, and Discussion in separate modules
2. present mathematical formulation before implementation details
3. make Results claim-driven rather than metric-driven

Hard constraints:

- avoid meta-lines such as "This section shows..." or "The purpose of this figure is..."
- do not mix code flags or configuration names into the main mathematical narrative
- do not add unsupported statistical language

## 6. Phase 3: Unification And Style Alignment

Tasks:

1. merge approved modules into a full manuscript
2. remove verbose transitions and AI-sounding filler
3. enforce terminology consistency across the manuscript
4. elevate the Discussion with moderate biological or practical meaning

Acceptable uplift:

- frame the model as an in silico hypothesis-generation tool

Unacceptable uplift:

- claim clinical readiness without evidence
- claim direct drug-development utility without evidence

## 7. Phase 4: Typesetting And Asset Integration

Tasks:

1. write self-contained figure captions
2. generate venue-appropriate LaTeX
3. produce manuscript assets such as Markdown, LaTeX, PDF, or related deliverables when possible

Captions must explain:

- what each panel shows
- what the metric means or which direction is better
- what each axis represents
- what main claim the figure supports

Never invent:

- p-values
- error-bar definitions
- sample sizes
- statistical tests

Equation policy:

- number only core equations that will be referenced later
- do not number every displayed equation

## 8. Phase 5: Deep QA

Always check:

- figure overflow
- caption placement
- equation overflow
- citation and reference-list alignment
- blind-review compliance
- Data and Code Availability statements

When direct rendered-page inspection is not available, perform code-level checks before claiming the manuscript is safe:

- verify that figures use bounded widths such as `\includegraphics[width=\linewidth]{...}` or another explicit max-width choice
- verify that figure environments use reasonable placement hints such as `[htbp]` rather than forcing fragile layouts
- verify that wide equations are wrapped with environments such as `split`, `aligned`, or another line-breaking strategy instead of overflowing the right margin
- verify that oversized content is handled with explicit width control rather than assuming the template will fix it automatically

Required output:

- a QA report
- corrected final manuscript assets

## 9. Global Writing Floor

- Results must be discovery-driven, not a metric directory
- every figure, table, and case study must serve a claim
- do not freeze citation style before the venue is fixed
- before the venue is fixed, prioritize consistency between in-text citations and the reference list
