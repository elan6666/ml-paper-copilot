# Internal Red-Team Review

Use this reference for silent self-correction in Phase 1. Never print this checklist verbatim to the user.

## Severity Gates

- `CRITICAL`: the central claim is not supported, the logic chain breaks, or the paper would likely be rejected for core validity reasons
- `MAJOR`: a key claim is overstated, the comparison is unfair, or a section lacks enough evidence to defend its conclusion
- `MINOR`: wording, emphasis, or structure can be tightened without changing the scientific core

## Core Attack Directions

### 1. Overclaiming
- challenge every claim that extends beyond the provided evidence
- remove language that implies generality, causality, or deployment readiness unless the material directly supports it
- downgrade claims that turn benchmark wins into broad scientific conclusions

### 2. Logic-Chain Breaks
- verify that problem, method, result, and conclusion form a continuous argument
- flag any place where a claim depends on an unstated assumption
- reject paragraphs whose conclusion is stronger than the observations that precede it

### 3. Unfair Comparison
- check whether baselines, ablations, and data splits are described consistently
- flag any comparison that mixes different datasets, settings, or preprocessing without saying so
- reject wins based only on selective metrics when the full picture is weaker

### 4. Cherry-Picking And Confirmation Bias
- ask whether the selected figures or examples hide contradictory evidence
- force the narrative to mention known limitations, failure cases, or scope boundaries
- avoid treating a best-case example as representative behavior

### 5. Unsupported Implications
- remove downstream biological or practical implications that are not grounded in the results
- allow useful framing such as hypothesis generation, but do not imply clinical or production readiness without evidence

## Rewrite Triggers

Trigger a rewrite when any of the following appears:
- a sentence can be read as stronger than the data warrants
- a section lacks a direct bridge between evidence and claim
- the method is praised for robustness without a robustness result
- fairness of comparison is ambiguous
- limitations are absent where a reasonable reviewer would expect them

## Output Discipline

The user should only see the corrected manuscript and the final QA summary. Internal attacks stay internal.
