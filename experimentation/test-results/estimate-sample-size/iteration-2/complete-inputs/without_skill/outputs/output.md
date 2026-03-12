# A/B Test Sample Size Estimate: Food Delivery App

## Test Configuration
- **Test Type:** Two-proportion A/B test (restaurant card design)
- **Primary Metric:** Click-to-order conversion rate
- **Confidence Level:** 95% (α = 0.05, two-tailed)
- **Statistical Power:** 80% (β = 0.20)
- **Split:** 50/50 (Control vs Treatment)

## Baseline and Effect
- **Baseline Conversion Rate (p₀):** 7.8%
- **Minimum Detectable Effect (MDE):** +0.8 percentage points
- **Expected Treatment Conversion Rate (p₁):** 8.6% (7.8% + 0.8%)
- **Relative Lift:** 10.26% [(8.6 - 7.8) / 7.8]

## Statistical Parameters
- **Z-score for 95% confidence (α/2 = 0.025):** 1.96
- **Z-score for 80% power (β = 0.20):** 0.84
- **Z-critical (one-sided):** 2.8 (1.96 + 0.84)

## Sample Size Calculation

### Formula
n = (Z_{α/2} + Z_β)² × [p₀(1-p₀) + p₁(1-p₁)] / (p₁ - p₀)²

### Variance Calculation
- p₀(1-p₀) = 0.078 × 0.922 = 0.071916
- p₁(1-p₁) = 0.086 × 0.914 = 0.078604
- Pooled variance = 0.150520

### Effect Size
- (p₁ - p₀)² = (0.008)² = 0.000064
- Z-critical squared = 7.84

### Result per Group
n = (7.84 × 0.150520) / 0.000064 = **117,752 users per group**

## Sample Size Requirements

| Metric | Value |
|--------|-------|
| **Per Group (50/50 split)** | 117,752 users |
| **Total Sample Size** | 235,504 users |
| **Control Group** | 117,752 users |
| **Treatment Group** | 117,752 users |

## Feasibility Analysis
- **Weekly Eligible Traffic:** 35,000 users/week
- **Test Duration Required:** 235,504 ÷ 35,000 = **6.73 weeks** (~47 days)
- **Recommended Duration:** 7 weeks (to account for day-of-week variations)
- **Status:** ✓ Feasible within typical testing windows

## Power Analysis
- **Significance Level (α):** 0.05
- **Power (1 - β):** 0.80 (80% chance of detecting the effect if real)
- **Type I Error (false positive):** 5%
- **Type II Error (false negative):** 20%

## Critical Values
- **Minimum observed difference to reject null hypothesis:** Approximately ±0.0053 (0.53 pp at baseline rate)
- **Confidence Interval at significance:** ±0.0053 around observed difference

## Recommendations

1. **Sample Size:** Allocate **117,752 users to each variant** for a total of **235,504 users**
2. **Duration:** Plan for a **7-week test** given 35,000 weekly eligible users
3. **Monitoring:** Use sequential testing or set fixed end-date to avoid multiple comparison issues
4. **Traffic Allocation:** Maintain 50/50 split unless business constraints require adjustment
5. **Minimum Duration:** Run for at least 2 weeks (minimum 70,000 users) to capture weekly variations
6. **Sanity Checks:** Verify random assignment, tracking implementation, and metric definition before launch

## Notes
- This calculation assumes normal approximation to binomial distribution (valid for these proportions)
- Real-world factors like seasonality, user segments, and device types may require higher sample sizes
- If MDE of 0.8pp is difficult to achieve, consider re-evaluating the effect size or accepting higher Type II error
- 80% power is standard but conservative; 90% power would require ~157,000 per group (6.73 weeks → 8.95 weeks)
