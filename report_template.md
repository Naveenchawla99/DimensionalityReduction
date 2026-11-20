# Reduce or not? Olivetti faces (400 × 4,096)

*Target 1,200–2,000 words. Fill every [bracket] from the script output.*

## R1. Data and task
Olivetti faces (AT&T, via scikit-learn): n = 400, d = 4,096 pixel columns. Task: 40-class identity classification, logistic regression, stratified 5-fold CV, seed 42.

## R2. Scree finding
Table: components for 80/90/95/99% for faces vs noise control; first five ratios.
Two sentences: [Redundant? Why, in terms of what pixels measure.] [What the noise control shows.]

## R3. Own PCA checked
Four checks (components, explained variance, projections, reconstruction): [pass/fail each]. Dense 4096×4096 covariance ≈ 134 MB, so the dense route was feasible.

## R4. What reduction costs
Insert `table_R4.csv`. All reduction inside a Pipeline.
- Gap in rows (of 400) per k: [..]
- Gaps inside the fold std reported as "no measurable cost": [which]
- k = d is impossible because d > n; the full row uses k = 319 (training-fold rank) and should match "none": [does it?]

## R5. Extraction vs selection
Insert `table_R5.csv`. Direction: [PCA or selection wins]. Case: [tumour-like redundancy / low-variance signal], shown by [numbers].

## R6. One honest picture
PCA: trustworthiness [..], kNN overlap [..]. t-SNE (perplexity 5/15/30/50): [..]; stability [..]. t-SNE cannot embed new data. Chosen: [..] because [..].
Figure: `final_figure.png`
**Caption:** Axes are [PCA components / t-SNE coordinates with no intrinsic meaning]. Distance means [global variance directions / only local neighbourhood]. Do not conclude [e.g. that cluster gaps or sizes reflect real separation between people].

## R7. Decision (≤ 400 words)
Reduce or not: [..]. k = [..]. Constraint: [concrete: d vs n, model size, etc., with a computed figure]. Evidence: [R4, R5 numbers]. What the scree established anyway: [..].

## R8. Robustness
1. CV seeds 0/1/2: [does any conclusion move?] Effect on R7: [..]
2. No standardisation: components [..], score [..]. Effect on R7: [..]

## Limits
[One paragraph, e.g. k = d replaced by rank cap; R9 not attempted; results from one dataset and one model; anything that failed.]
