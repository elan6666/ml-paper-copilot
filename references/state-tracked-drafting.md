# State-Tracked Drafting

Use this protocol to prevent long-manuscript drift.

## State Object
Use `templates/paper-state.yaml` as the canonical internal schema.

Track at least:
- venue and template choice
- core claims
- figure-to-claim map
- section order
- section summaries
- citation gaps
- open risks and unresolved TODOs

## Drafting Loop

1. Initialize state from Phase 0 inputs.
2. Draft one section or subsection at a time.
3. After each section, compress it into a 5 to 10 line state summary.
4. Store any unresolved evidence gaps, citation gaps, or notation decisions in state.
5. Draft the next section from the state object plus source materials.
6. Repeat until the manuscript is complete.

## Compression Rules
- keep summaries factual and operational
- record what the section claims, what evidence it uses, and what caveats remain
- do not copy full paragraphs into state
- preserve terminology exactly when the paper uses specialized phrases

## Continuity Rules
- treat state as the ground truth for progress
- when a later section conflicts with existing state, resolve the inconsistency before continuing
- update earlier summaries if a later rewrite changes a claim or limitation

## Final Pass
Before LaTeX assembly, confirm that:
- every main section has a state summary
- all figure references map to actual claims
- all open risks are either resolved or surfaced in QA
