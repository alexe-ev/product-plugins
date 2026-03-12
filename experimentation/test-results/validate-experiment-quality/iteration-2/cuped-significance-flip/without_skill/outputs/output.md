# Experiment Quality Assessment: Simplified Notification Preferences UI

## Summary of Findings

This experiment exhibits **significant trustworthiness concerns** that should prevent immediate shipping. While the post-adjustment result (p=0.028) appears statistically significant, critical issues with the analysis methodology and covariate specification undermine confidence in this conclusion.

## Key Quality Issues

### 1. Unadjusted Result Does Not Meet Significance Threshold
The **raw, pre-adjustment result is not statistically significant**:
- p-value: 0.091 (above standard α=0.05 threshold)
- Observed effect: +0.7 percentage points
- Pre-planned MDE: +1.0 percentage points

The observed effect falls **below the minimum detectable effect** and fails to achieve statistical significance in the planned primary analysis. This is a critical finding that cannot be overlooked.

### 2. Large Significance Flip Requires Scrutiny
The shift from p=0.091 (unadjusted) to p=0.028 (variance-reduced) represents a **dramatic change in statistical significance**. This magnitude of change suggests that the pre-experiment engagement covariate explained a substantial share of the outcome variance. While variance reduction is a legitimate statistical technique, a shift of this magnitude warrants careful verification:

- **Did the covariate remove genuine noise or genuine signal?**
- **Is the covariate measurement itself reliable and uncontaminated?**

A large variance reduction effect can indicate either legitimate noise reduction or potential data quality issues that require investigation.

### 3. Critical Covariate Specification Gaps
The covariate specification "pre-experiment engagement" is **severely underspecified** and creates material risk of data contamination:

- **No metric definition**: What exactly is "engagement"? Users per day? Session count? Time on site? Feature adoption rate?
- **No time window specified**: What constitutes "pre-experiment"? 7 days? 30 days? 90 days?
- **No confirmation of non-overlap**: Most critically, is it confirmed that the pre-experiment measurement window does **not overlap with the test period**?

If the "pre-experiment" window includes any days during the 21-day test period, the covariate becomes **post-treatment measurement** that itself responds to the treatment, inducing bias rather than reducing it.

### 4. Multiple Comparisons and P-Hacking Risk
The team has effectively conducted two statistical tests:
1. Raw analysis (p=0.091)
2. Post-adjustment analysis (p=0.028)

Only reporting the second result while the first was exploratory creates **p-hacking optics**. Standard practice when applying variance reduction should be pre-registration or explicit reporting of both analyses.

## Recommendations Before Shipping

**Do not ship based on the adjusted p=0.028 result without:**

1. **Verify covariate specification in writing**: Document the exact metric definition, the precise pre-experiment time window (with confirmed non-overlap), and the data source for the covariate measurement.

2. **Confirm no data leakage**: Verify through audit that no measurements used in the covariate span any part of the test period (including the start date).

3. **Report results transparently**: Present both the raw (p=0.091) and adjusted (p=0.028) results as co-equal evidence. If shipping is approved, document the variance reduction adjustment in release notes and monitoring specifications.

4. **Set heightened monitoring**: Because the signal is borderline even after adjustment, implement intensive post-launch monitoring of the opt-in metric for at least 2 weeks to detect any reversal or unexpected behavior.

5. **Consider extended follow-up**: If the 7-day opt-in rate is the business target, confirm the effect persists in longer-term follow-up (14-day or 30-day opt-in rates).

## Conclusion

The experiment is **not currently trustworthy as presented** due to underspecified methodology, a dramatic significance flip that raises questions about covariate contamination, and the practice of reporting only the favorable adjusted result. Addressing these gaps through verification and transparent reporting is essential before treating this result as a basis for product decisions.
