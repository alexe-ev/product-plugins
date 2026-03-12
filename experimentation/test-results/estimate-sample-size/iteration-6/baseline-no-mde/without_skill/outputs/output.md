# A/B Test Sample Size Estimation

## Missing Required Input: MDE

To calculate sample size for your A/B test, I need one more critical input: **your Minimum Detectable Effect (MDE)** — the smallest improvement you want to reliably detect.

Here's why this matters: Sample size scales inversely with effect size. A smaller improvement requires a much larger sample to detect reliably, while a larger improvement needs fewer users.

## Your Parameters

- **Baseline CTR:** 8.2%
- **Weekly traffic:** 15,000 users
- **Confidence level:** 95% (α = 0.05)
- **Statistical power:** 80% (β = 0.20)

## Sample Size Estimates by MDE Scenario

### Scenario 1: +0.5 percentage points (8.2% → 8.7%)
- **Assumed MDE:** +0.5pp
- **Sample per variant:** ~36,000 users
- **Total sample (both variants):** ~72,000 users
- **Duration to reach sample:** ~4.8 weeks of traffic
- **Use case:** Conservative improvement target; high confidence in detecting modest gains

### Scenario 2: +1.0 percentage point (8.2% → 9.2%)
- **Assumed MDE:** +1.0pp
- **Sample per variant:** ~9,000 users
- **Total sample (both variants):** ~18,000 users
- **Duration to reach sample:** ~1.2 weeks of traffic
- **Use case:** Moderate improvement target; practical for typical feature tests

### Scenario 3: +2.0 percentage points (8.2% → 10.2%)
- **Assumed MDE:** +2.0pp
- **Sample per variant:** ~2,300 users
- **Total sample (both variants):** ~4,600 users
- **Duration to reach sample:** ~0.3 weeks (~2 days) of traffic
- **Use case:** Ambitious improvement target; appropriate for high-impact changes

## Next Steps

To determine your actual sample size requirement, decide:

1. **What's the smallest improvement that would be worth implementing?** This becomes your MDE.
2. **What's realistic given your development costs and opportunity cost of the test duration?**
3. **What precedent exists in your organization for similar changes?**

Once you settle on an MDE, I can refine the sample size calculation and provide a concrete duration estimate.
