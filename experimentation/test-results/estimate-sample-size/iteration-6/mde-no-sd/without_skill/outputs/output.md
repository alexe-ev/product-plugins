# A/B Test Sample Size Calculation: Onboarding Flow

## Test Parameters
- **Primary metric**: Time to first action (continuous, minutes)
- **Baseline**: 8 minutes average
- **Minimum detectable effect (MDE)**: 0.5 minutes (30 seconds)
- **Confidence level**: 95% (α = 0.05, two-tailed)
- **Power**: 80% (β = 0.20)
- **Eligible traffic**: 3,000 new users/week

## Critical Missing Input: Standard Deviation

**I cannot provide a single definitive sample size without the standard deviation (SD) of your baseline metric.** The variability in time-to-first-action is a required input for the power calculation, and it directly affects sample size.

## The Formula

Sample size per group:
```
n = 2 × (z_α/2 + z_β)² × σ² / (Δ)²
```

Where:
- z_α/2 = 1.96 (95% confidence, two-tailed)
- z_β = 0.84 (80% power)
- Δ = 0.5 minutes (your MDE)
- **σ = standard deviation (UNKNOWN)**

## How to Obtain Standard Deviation

### Option 1: Historical Data (Recommended)
Extract time-to-first-action data from your analytics for past weeks/months of users in the control condition. Calculate the sample standard deviation.

### Option 2: Pilot Test
Run a small pilot with the new design (100-200 users) to estimate variance before full rollout.

### Option 3: Prior Experiments
Review results from previous onboarding tests in your system to see historical SD values for similar metrics.

### Option 4: Benchmarking
Industry reports sometimes publish typical onboarding metrics, though these won't be specific to your product.

## Scenario Estimates

These illustrate how sensitive sample size is to the SD assumption:

| Assumed SD | n per group | Total n | Weeks to reach |
|-----------|-----------|---------|----------------|
| 1.5 min   | 189       | 378     | <1 week        |
| 2.0 min   | 252       | 504     | <1 week        |
| 3.0 min   | 568       | 1,136   | <1 week        |
| 4.0 min   | 1,010     | 2,020   | <1 week        |
| 5.0 min   | 1,575     | 3,150   | ~1 week        |

All scenarios are achievable with your eligible traffic of 3,000/week.

## Next Steps

1. **Determine your baseline SD** using historical data (preferred method)
2. Use that SD to calculate exact sample size
3. Run your test with equal allocation (50/50) for control/test
4. Collect at least the calculated n per group before analyzing results
