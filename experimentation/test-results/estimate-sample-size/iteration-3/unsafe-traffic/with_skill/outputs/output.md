# Sample Size Estimation: B2B Onboarding Wizard

## Executive Summary
For a B2B project management tool testing a new onboarding wizard, you need approximately **1,537 users per group** (3,074 total users) to reliably detect a +5 percentage point improvement in onboarding completion rate from the baseline of 41% to 46%, at 95% confidence with 80% statistical power.

With 3,750 eligible new sign-ups per month, the test can be completed in approximately **3.6 weeks**.

---

## Calculation Details

### Inputs Used
- **Metric type:** Conversion / Rate metric
- **Primary metric:** Onboarding completion rate
- **Baseline completion rate (p1):** 41% (0.41)
- **Minimum detectable effect:** +5 percentage points
- **Target completion rate (p2):** 46% (0.46)
- **Confidence level:** 95% (two-sided) → z_α/2 = 1.96
- **Statistical power:** 80% → z_β = 0.84
- **Eligible traffic:** 3,750 new sign-ups per month (15% of 25,000 registered users)
- **Split ratio:** 50/50 (assumed)

### Conversion Metric Formula
Using the explicit formula from REFERENCE.md:

```
n_per_group = (z_α/2 + z_β)² × (p1×(1−p1) + p2×(1−p2)) / (p2 − p1)²
```

### Step-by-Step Calculation

**Step 1: Calculate z-value sum squared**
- (z_α/2 + z_β)² = (1.96 + 0.84)² = (2.80)² = **7.84**

**Step 2: Calculate variance term for baseline rate (p1)**
- p1 × (1 − p1) = 0.41 × 0.59 = **0.2419**

**Step 3: Calculate variance term for target rate (p2)**
- p2 × (1 − p2) = 0.46 × 0.54 = **0.2484**

**Step 4: Sum the variance components**
- 0.2419 + 0.2484 = **0.4903**

**Step 5: Calculate squared effect size**
- (p2 − p1)² = (0.46 − 0.41)² = (0.05)² = **0.0025**

**Step 6: Calculate numerator**
- 7.84 × 0.4903 = **3.8408**

**Step 7: Calculate sample size per group**
- n_per_group = 3.8408 / 0.0025 = **1,536.32 ≈ 1,537 users per group**

**Step 8: Calculate total sample size**
- Total sample = 1,537 × 2 = **3,074 users total**

**Step 9: Estimate test duration**
- Eligible new sign-ups per month = 25,000 × 0.15 = 3,750
- Duration = 3,074 / 3,750 = **0.82 months ≈ 3.6 weeks**

---

## Results Summary

| Metric | Value |
|--------|-------|
| Sample size per group | 1,537 users |
| Total sample size | 3,074 users |
| Estimated duration | 3.6 weeks |
| Eligible traffic per month | 3,750 new sign-ups |

---

## Assumptions Made

1. **Two-variant fixed-horizon A/B test** with even 50/50 split between control and treatment
2. **Stable traffic quality** throughout the test period (no major shifts in onboarding funnel)
3. **Eligible traffic** refers specifically to new sign-ups entering the onboarding wizard—not all 25,000 registered users
4. **Linear behavior:** The onboarding completion behavior remains consistent across the test window
5. **No confounding factors** such as seasonal variation in onboarding patterns, major product changes, or promotional campaigns that would alter traffic composition during the test period
6. **Conversion measurement:** Completion rate is measured consistently and without ambiguity

---

## Feasibility Assessment

**Status: Feasible**

- **Traffic sufficiency:** With 3,750 eligible new sign-ups per month, you have sufficient traffic to complete the test in roughly one month. This is well-aligned with typical product development cycles.
- **Effect size realism:** A +5 percentage point improvement (from 41% to 46%) is a meaningful and realistic business objective for an onboarding improvement.
- **Duration:** 3.6 weeks is a reasonable test window that fits standard sprint or planning cycles.

**Potential considerations:**

- If new sign-up volume drops during holidays or seasonal troughs, duration may extend.
- If the onboarding wizard change also affects lower-funnel metrics (e.g., product adoption after completion), consider monitoring those as secondary metrics to understand the full impact.
- Ensure that the definition of "completion" is clear and logged consistently in your analytics.

---

## Missing or Optional Inputs

- **Weekly or daily traffic breakdown:** Not provided; assumed evenly distributed across the month.
- **Exclusions or segments:** None specified; assumes all eligible new sign-ups are included.
- **Secondary metrics:** Not specified; recommend monitoring adoption and retention post-onboarding.
- **Split ratio details:** Assumed 50/50; if a different allocation is preferred, sample sizes per group would adjust accordingly.

---

## Next Steps

1. **Confirm the baseline rate:** Verify that 41% onboarding completion is accurate from recent data.
2. **Validate traffic assumptions:** Check that 3,750 new sign-ups per month is accurate for your current period.
3. **Define completion clearly:** Ensure the team agrees on what constitutes a completed onboarding (final step submission, feature adoption, etc.).
4. **Plan analytics setup:** Ensure you can reliably assign users to variant groups and measure completion status.
5. **Schedule the test:** With ~3.6 weeks needed, plan to launch at a time that avoids major holidays or planned maintenance windows.
6. **Set up early-stopping rules (optional):** If your infrastructure supports sequential testing, you may be able to conclude the test earlier if a clear signal emerges.

---

## Trust Caveats

- This estimate assumes the eligible traffic figure (3,750 per month) is accurate and represents users actually entering the onboarding flow.
- If a significant fraction of new sign-ups bypass or skip the onboarding, the duration will be longer.
- Results are valid only if the test runs for the full duration without external factors (e.g., major feature launches, competitor actions) that would materially shift user behavior.
