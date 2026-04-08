# Citation Workflow

This repository uses a strict `.bib`-only policy.

## Source Of Truth
- the user-provided `.bib` file is the only bibliography source of truth
- do not search the web, query APIs, or invent citation metadata
- do not create new bibliography entries from memory

## Required Workflow

1. Read the provided `.bib` file and extract the available citation keys.
2. Build a local key inventory before drafting the manuscript.
3. Insert `\cite{key}` only when `key` exists in the provided inventory.
4. If support is missing for a desired citation, remove the unsupported citation and note the gap in QA.
5. Keep citation style compatible with the selected bundled template.

## Citation-Key Rules
- keep user-provided keys unchanged
- do not rename keys unless the user explicitly asks
- do not normalize or rewrite bibliography entries silently

## Missing Citation Handling
- acceptable: omit the unsupported citation and mention it in QA
- unacceptable: invent a new key, fabricate an entry, or cite a paper from memory

## Drafting Guidance
- cite only where a reference materially supports a factual statement, method lineage, or comparison claim
- do not add decorative citations to make text look scholarly
- if the exact supporting reference is missing from `.bib`, write the sentence more conservatively

## QA Expectations
The final QA note should mention:
- missing citation support that prevented a `\cite{}` insertion
- template-specific bibliography assumptions, if any
- any unresolved mismatch between the desired narrative and the provided `.bib`
