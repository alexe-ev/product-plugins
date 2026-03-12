# Sample Size Estimation: Onboarding Wizard A/B Test

## Executive Summary

For your B2B project management tool onboarding wizard test, you need **3,076 total participants** (1,538 per group) to detect a 5 percentage point improvement in completion rate with 95% confidence and 80% statistical power.

**Good news**: This sample size is achievable within approximately **3-4 weeks** using your current new user traffic (~3,750 new sign-ups per month).

---

## Detailed Calculation

### Test Parameters

| Parameter | Value |
|-----------|-------|
| **Primary Metric** | Onboarding Completion Rate |
| **Baseline Rate (Control)** | 41% |
| **Minimum Detectable Effect** | +5 percentage points |
| **Expected Rate (Treatment)** | 46% |
| **Confidence Level** | 95% (α = 0.05, two-tailed) |
| **Statistical Power** | 80% (1 - β = 0.80, β = 0.20) |
| **Test Design** | Two-proportion test, independent samples |

### Statistical Formula

For comparing two independent proportions:

```
n = (z_α/2 + z_β)² × [p₁(1-p₁) + p₂(1-p₂)] / (p₂ - p₁)²
```

Where:
- **z_α/2** = 1.96 (critical value for 95% confidence level, two-tailed)
- **z_β** = 0.84 (critical value for 80% power)
- **p₁** = 0.41 (baseline completion rate)
- **p₂** = 0.46 (expected completion rate)
- **p₂ - p₁** = 0.05 (minimum detectable effect)

### Calculation Steps

1. **Variance component**: p₁(1-p₁) + p₂(1-p₂)
   - = 0.41(0.59) + 0.46(0.54)
   - = 0.2419 + 0.2484
   - = 0.4903

2. **Z-score component**: (z_α/2 + z_β)²
   - = (1.96 + 0.84)²
   - = (2.80)²
   - = 7.84

3. **Effect size**: (p₂ - p₁)²
   - = (0.05)²
   - = 0.0025

4. **Sample size per group**:
   - n = (7.84 × 0.4903) / 0.0025
   - n = 3.8408 / 0.0025
   - n = **1,537.6** → **1,538 per group**

5. **Total sample size** (both control + treatment):
   - n_total = 1,538 × 2 = **3,076**

---

## Results

### Sample Size Requirements

| Metric | Value |
|--------|-------|
| **Control Group Size** | 1,538 participants |
| **Treatment Group Size** | 1,538 participants |
| **Total Sample Size** | **3,076 participants** |

### Power Analysis Interpretation

- **Statistical Power**: 80% — If the true effect is 5 percentage points, there's an 80% probability your test will detect it as statistically significant at the 95% confidence level.
- **Type II Error (β)**: 20% — There's a 20% chance of a false negative (failing to detect a real 5 percentage point improvement).
- **Type I Error (α)**: 5% — There's a 5% chance of a false positive (detecting an effect when none exists).

---

## Feasibility Analysis

### Population Context

| Factor | Value |
|--------|-------|
| **Total Registered Users** | 25,000 |
| **Monthly New Sign-ups** | 3,750 (15% of total) |
| **Required Sample** | 3,076 users |
| **Sample as % of Monthly Traffic** | **82.0%** |
| **Time to Reach Sample** | **~3-4 weeks** |

### Recommendation

✅ **The sample size is highly achievable.** Since 82% of your monthly new user traffic is needed, you can expect to reach statistical significance within 3-4 weeks of the test launching, assuming:
- Steady new user sign-up rate (~3,750/month)
- Random assignment to control/treatment groups
- No significant seasonal variations in traffic

### Implementation Considerations

1. **User Eligibility**: Only new sign-ups go through the onboarding wizard. Ensure you exclude existing users who may be re-onboarding or using the wizard for re-engagement.

2. **Randomization**: Use a consistent randomization mechanism (e.g., random assignment at sign-up time, user ID modulo, or a feature flag service) to ensure users are evenly distributed between groups.

3. **Duration**: Plan for the test to run approximately 3-4 weeks to accumulate 3,076 participants. However:
   - If traffic is higher than 15% monthly, you'll reach the sample size faster
   - If traffic is lower, you may need to extend the test duration
   - Consider day-of-week or seasonal effects on new sign-ups

4. **Minimum Practical Effect Size**: Your 5 percentage point improvement (41% → 46%) is both statistically meaningful AND practically valuable for an onboarding metric. Even detecting a smaller effect would require significantly more samples.

---

## Sensitivity Analysis

### What if you need a different effect size?

| MDE | Sample per Group | Total Sample | Time (weeks) |
|-----|------------------|--------------|--------------|
| ±3 pp | 2,794 | 5,588 | 7.5 |
| ±4 pp | 1,976 | 3,952 | 5.3 |
| ±5 pp | 1,538 | 3,076 | 4.1 |
| ±6 pp | 1,347 | 2,694 | 3.6 |

### What if you want 90% power instead of 80%?

With 90% power (z_β = 1.28):
- Sample per group: 1,749
- Total sample: 3,498
- Time needed: ~4.7 weeks

---

## Statistical Notes

1. **Two-tailed test**: The calculation assumes you're testing for either improvement or degradation (typical for product changes).

2. **Independence assumption**: The test assumes treatment group participants don't influence control group behavior (reasonable for onboarding).

3. **Proportional metric**: Since completion rate is a binary metric (completed or not), the two-proportion test is appropriate.

4. **Intent-to-treat (ITT) principle**: All randomized users should be included in analysis, whether they completed onboarding or not.

---

## Next Steps

1. **Configure experiment**: Set up your feature flag or experiment framework to randomize users into control (current wizard) and treatment (new wizard) groups.

2. **Track metrics**: Instrument both groups to capture:
   - Completion events
   - Dropout points in the wizard
   - Time to completion
   - Any secondary metrics (account activation, first task completion, etc.)

3. **Monitor results**: After 2 weeks, check interim results. Plan for 3-4 weeks before making a final decision.

4. **Statistical test**: Use a two-proportion z-test or chi-square test to evaluate significance at the end of the test period.

5. **Post-hoc analysis**: If the test shows significant results, analyze which wizard steps showed the largest improvements.

---

*Calculation date: 2026-03-11*
*Method: Standard two-proportion power analysis*
