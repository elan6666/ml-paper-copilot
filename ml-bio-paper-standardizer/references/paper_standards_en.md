# Standards for computational biology and machine learning method papers

## 1. Core positioning

This type of paper should not merely show that "the metric is higher". It should establish that:

1. the method achieves a stable advantage on standard benchmarks;
2. this advantage comes from the right mechanism rather than fitting generic shifts or dataset bias;
3. the advantage appears not only in mean-level metrics, but also in distribution structure, generalization, and biological interpretability.

## 2. Structure

Default structure:

1. Abstract
2. Introduction
3. Methods
4. Results
5. Discussion and conclusion
6. Data and code availability
7. Acknowledgements
8. References

If the paper is explicitly targeted at a Nature-family venue, consider:

1. Introduction
2. Results
3. Discussion
4. Methods
5. References

## 3. Writing style

### Must do

- State findings directly in the Results section.
- Write subsection titles as claims or conclusions.
- Use prior work as objective evidence.
- Make figures, metrics, and case studies serve the main claims.

### Do not do

- "This conclusion is supported by Fig. ..."
- "The role of this figure is ..."
- "The point here is not ... but ..."
- "We first answer the following question ..."

## 4. Methods

The Methods section should be split into:

- problem formulation
- mathematical formulation
- training objectives
- predictive performance metrics
- implementation details

Principles:

- Use mathematical language for the main formulation: objects, variables, objectives, and data flow.
- Move hyperparameters, default configurations, and code flags to implementation details.

## 5. Results

Results must be story-driven rather than metric-driven.

Recommended order:

1. standard benchmark
2. mechanistic evidence beyond systematic variation
3. recovery of condition-level distribution structure
4. difficult extrapolation / unseen perturbation generalization
5. biological recovery

## 6. Equations

- Number only core equations.
- Typical candidates include:
  - the main problem definition
  - the key optimization objective
  - the joint loss
  - definitions of mechanism-focused metrics
- Do not force numbering on every displayed equation.

## 7. Citations

- Do not force the final citation style before the target venue is fixed.
- If the target is a Nature-family venue, superscript numeric citations may be appropriate.
- If the target venue is not fixed, prioritize consistency and one-to-one alignment between in-text citations and the reference list.

## 8. Figure captions

Captions must be self-contained and at least explain:

- what each panel measures;
- what the metric means;
- what each axis represents;
- what the case-study plot shows;
- what main conclusion the figure supports.

Do not claim information that is not actually present:

- error-bar definitions
- sample size
- statistical tests
- p-values

Only add these details when they truly exist in the figure or the underlying analysis.

## 9. Discussion

The Discussion section should include:

- a summary of the main findings
- the mechanistic meaning of the method
- limitations
- future directions
- a moderate statement of biological or practical significance

Acceptable uplift:

- "The model is not only a predictor, but also an in silico hypothesis-generation tool."

Unacceptable uplift:

- unsupported claims of clinical or drug-development readiness

## 10. Figure-to-notebook alignment

Notebooks must serve the paper narrative, not the other way around. Each figure should have a fixed narrative role, rather than mixing benchmarking, mechanism analysis, and biology in a single figure.

## 11. Final checks

Before exporting PDF or Word, always verify:

- page headers and footers are correct
- legends do not overlap the plot body
- figures and captions remain on the same page when possible
- equations render correctly
- titles do not collide with legends or exceed a sensible length
