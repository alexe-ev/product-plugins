# Sample Size Estimation: B2B Onboarding Wizard

## Executive Summary

**Critical Context Alert:** The user provided total platform users (25,000) but only a fraction is eligible for the onboarding test. Only new sign-ups can be tested, which represents approximately 15% of the platform = **3,750 eligible users per month**.

This is the key distinction: the sample size estimation proceeds normally, but the **duration estimate must be based on eligible traffic only, not total platform traffic**.

---

## Inputs Used

| Parameter | Value | Notes |
|-----------|-------|-------|
| Primary Metric | Onboarding completion rate | Conversion-style metric |
| Baseline (p1) | 41% (0.41) | Current completion rate |
| Target (p2) | 46% (0.46) | 41% + 5 percentage points |
| Minimum Detectable Effect | +5 percentage points (absolute) | User-specified uplift |
| Confidence Level | 95% | Two-tailed significance level (α = 0.05) |
| Statistical Power | 80% | (β = 0.20, z_β = 0.84) |
| **Total Registered Users** | 25,000 | Platform-wide user base |
| **Eligible Traffic (New Sign-ups)** | 15% of platform = **3,750 users/month** | Only new sign-ups see onboarding |
| Split Ratio | 50/50 (assumed) | Equal assignment to control and treatment |

---

## Sample Size Calculation

### Formula (Two-Proportion Test)

```
n = 2 * [(z_α/2 + z_β)² * (p1(1-p1) + p2(1-p2))] / (p2 - p1)²
```

### Parameters

- z_α/2 = 1.96 (for 95% confidence, two-tailed)
- z_β = 0.84 (for 80% power)
- p1 = 0.41 (baseline)
- p2 = 0.46 (target)
- Effect size (p2 - p1) = 0.05

### Step-by-Step Calculation

```
Numerator: 2 * [(1.96 + 0.84)² * (0.41 × 0.59 + 0.46 × 0.54)]
         = 2 * [(2.80)² * (0.2419 + 0.2484)]
         = 2 * [7.84 × 0.4903]
         = 2 * 3.8416
         = 7.6832

Denominator: (0.05)² = 0.0025

n = 7.6832 / 0.0025 = 3,073.28
```

---

## Results

| Metric | Value |
|--------|-------|
| **Sample size per group (control)** | ~3,073 users |
| **Sample size per group (treatment)** | ~3,073 users |
| **Total sample size required** | ~6,146 users |

---

## Duration Estimation

### Why This Matters

The 25,000 total users **cannot be used** for duration calculation because:
- Existing, tenured users will not be re-exposed to the onboarding wizard
- Only new sign-ups see the onboarding flow
- **Eligible traffic = 15% of 25,000 = 3,750 new sign-ups per month**

### Duration Calculation

```
Estimated Duration = Total Required Sample / Eligible Traffic per Period
                   = 6,146 users / 3,750 users per month
                   = 1.64 months
                   ≈ 6.6 weeks
```

### Timeline

- **Conservative estimate (single variant):** ~7 weeks
- **Including overhead for analysis and validation:** ~8 weeks
- **Accounting for potential traffic variability:** ~8–10 weeks

---

## Assumptions

1. **Metric type:** Two-variant, fixed-horizon A/B test
2. **Equal split:** 50% of eligible new sign-ups assigned to control, 50% to treatment
3. **Traffic stability:** No major shifts in new sign-up rate across the test period
4. **No confounding:** Seasonal spikes, promotional campaigns, or shifts in user quality do not significantly distort results
5. **Single entry:** Each new sign-up user enters the onboarding flow once and cannot be re-assigned
6. **Completion measurement:** Completion is measured for all eligible users who enter, with no missing data on the outcome

---

## Feasibility Assessment

### Positive Factors

✓ The required sample size (6,146) is achievable within a reasonable 7–8 week window
✓ Monthly eligible traffic (3,750) is sufficient to power the test
✓ The effect size (+5 percentage points) is practically meaningful and statistically detectable

### Risk Factors

⚠ **Eligible traffic is limited:** With only 3,750 new sign-ups per month, the test cannot begin immediately if onboarding is released only to new users. If the team wants faster results, they may need to either:
   - Relax the minimum detectable effect
   - Lower power requirements below 80%
   - Lower confidence below 95%

⚠ **Month-to-month variability:** New user acquisition may fluctuate seasonally or due to product changes. If sign-up volume drops below 3,500/month, duration extends beyond 8 weeks.

⚠ **Completion rate uncertainty:** The baseline 41% completion rate should be verified across the user segments that will be included in the test. If completion varies by cohort, subgroup analysis may be needed.

---

## Missing Inputs (Optional, for refinement)

- **Exact eligible traffic breakdown:** Is the 15% figure per week, per month, or average? More granular traffic data would improve the confidence in the duration estimate.
- **Completion metric definition:** Is "onboarding completion" a binary outcome (finished/not finished) or a continuous score? Verify the metric aligns with the calculation.
- **Variance in new sign-up timing:** Do new users arrive uniformly, or does signup clustering (e.g., due to campaigns) affect the traffic profile?

---

## Summary & Recommendation

- **Sample size:** 6,146 total users (3,073 per group)
- **Estimated duration:** ~7 weeks based on 3,750 eligible new sign-ups per month
- **Feasibility:** Achievable, but depends critically on sustained new user acquisition

**Next steps:**
1. Confirm that new sign-up rates are stable at ~3,750/month
2. Verify the 41% baseline completion rate using recent cohort data
3. Plan test start date to account for ~8 weeks end-to-end (including setup, data collection, and analysis)
4. Monitor weekly acquisition to flag if sign-up rates drop and threaten the timeline

---

## Important Caveat

**Do not use total platform traffic (25,000 users) to estimate test duration.** Only users who enter the onboarding wizard—i.e., new sign-ups—can be assigned to variants. Using total users would underestimate duration by a factor of ~6.7x and is a common mistake in experimentation planning.
