# Methodology Checks

Use this reference during the internal review pass.

## Research Question Alignment
- state the target task clearly
- ensure every experiment directly addresses a claim in the paper
- reject auxiliary results that do not support the main argument

## Data And Splits
- confirm that training, validation, and test descriptions are internally consistent
- state when evaluation is in-distribution, out-of-distribution, cross-species, cross-patient, or otherwise shifted
- avoid hidden assumptions about labels, covariates, or preprocessing

## Baselines And Ablations
- describe the compared methods in a fair, minimally sufficient way
- confirm that the paper does not compare tuned results for one method against untuned defaults for another without disclosure
- require ablations when a claimed module or design choice is central to the story

## Metrics And Statistics
- explain why each metric is relevant to the scientific claim
- avoid metric dumping without interpretation
- do not fabricate significance tests, confidence intervals, or error bars
- if no uncertainty estimate is available, state the result conservatively

## Reproducibility
- describe the data source, model setting, and main training choices when available
- note missing hyperparameter, code, or data details in QA rather than inventing them
- ensure notation, symbols, and terminology stay consistent across sections

## Common Failure Modes
- conclusions that depend on one favorable metric only
- method descriptions that omit a critical assumption
- discussion sections that ignore limitations
- claims of robustness without explicit robustness experiments
- causal language for observational or predictive evidence
