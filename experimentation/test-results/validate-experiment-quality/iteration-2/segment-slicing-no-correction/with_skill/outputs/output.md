# Experiment Quality Validation: Email Personalisation Algorithm

## Quality Verdict
**Low Confidence**

## Major Risks

### 1. Post-Hoc Segment Slicing (Fatal)
The segment breakdown was conducted after observing the overall non-significant result (p=0.14). This is a classic case of post-hoc slicing—searching for statistical significance across subgroups only after the primary result failed to deliver.

Post-hoc slicing substantially inflates false-positive risk because the team had an outcome-dependent incentive to explore segments until one showed significance. This violates the principle of pre-specification and introduces selection bias into the analysis.

### 2. Uncontrolled Multiple Comparisons (Fatal)
The team tested 3 independent segments without a multiple-comparison correction. With three independent tests at α=0.05, the probability of at least one false positive is approximately 1 − (0.95)³ ≈ 14.3%.

The p-value of 0.031 for power users does not account for this multiplicity. Using the Bonferroni correction, the threshold for each test should be 0.05 ÷ 3 = 0.0167. The power-user result of p=0.031 does not meet this corrected threshold.

### 3. Inflated Type I Error Rate
Classical p-value interpretation assumes a single pre-registered test or valid correction for multiple looks. Neither condition is met here. The nominal false-positive rate of 5% is not trustworthy for this analysis.

### 4. Outcome-Dependent Exploration
The proposal to ship to power users relies on a result that only became "interesting" because the overall test was not significant. Without the initial failure, the segment exploration would not have occurred in the same way. This introduces selection bias and outcome-dependent reasoning.

## Reliability Level
**Low**

## Fatal vs Manageable Issues

| Issue | Severity | Reasoning |
|-------|----------|-----------|
| Post-hoc segment slicing | Fatal | Performed after observing overall non-significance; violates pre-specification principle |
| Multiple comparisons without correction | Fatal | Three uncorrected tests inflate false-positive probability to ~14%; power-user p=0.031 does not survive Bonferroni correction to α=0.0167 |
| Outcome-dependent analysis workflow | Fatal | Segments were selected for exploration because the primary metric failed; this is a classic data-driven false positive vulnerability |

## Recommendation
**Do not ship based on this analysis. Rerun or redesign.**

### Rationale
The power-user result of p=0.031 is not a valid basis for a shipping decision because:

1. It was discovered through post-hoc exploration after the primary test was non-significant
2. It does not account for the multiplicity of three segment tests
3. When corrected for multiple comparisons (Bonferroni: α=0.0167), the p-value of 0.031 is no longer statistically significant
4. The fact that power users are "the most valuable customers" does not justify ignoring the statistical validity concerns; it instead makes the false-positive risk more costly if the effect is not real

### Path Forward
If the team believes personalization works for power users, treat this as a **hypothesis-generating finding** and:

1. **Design a fresh, pre-registered experiment** targeting power users specifically
2. **Pre-register the primary metric** and stopping rule before running the test
3. **Avoid post-hoc exploration** during the test
4. **If interested in segments**, pre-register segment analyses with appropriate multiple-comparison corrections

This approach transforms a post-hoc observation into a testable hypothesis and restores procedural rigor.

## Missing Procedural Evidence
None critical—the strong procedural context (predefined sample size, predefined stopping rule, balanced traffic split, no major external events) is clearly documented. However, the critical missing evidence is:
- **Whether segment analysis was planned in advance.** The evidence suggests it was not; it appears to have been conducted only after observing the overall non-significant result.

## Summary
The overall experiment was well-run from a procedural standpoint. However, the post-hoc segment exploration introduces a fatal validity threat. Post-hoc slicing without correction is a known mechanism for false positives in experimentation. The team should not ship based on this result, and instead should design a confirmatory experiment if they want to pursue power-user personalization.
