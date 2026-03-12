# A/B Test Sample Size Estimation for Monetization Upsell Prompt

## Problem Setup
- **Metric:** Average Revenue Per User (ARPU)
- **Baseline ARPU:** $20
- **Baseline standard deviation:** $60
- **Minimum detectable effect (MDE):** +$3
- **Confidence level:** 95% (α = 0.05, two-tailed)
- **Power:** 80% (β = 0.20, so 1-β = 0.80)
- **Traffic:** 8,000 users/week, 50/50 split

## Critical Observation - High Variance Warning

The coefficient of variation (CV) = SD/Mean = $60/$20 = 3.0. This is extremely high and indicates the revenue distribution is heavily right-skewed with significant outliers. Revenue data typically follows a log-normal or exponential distribution rather than normal, which means the assumption of normality required for standard sample size calculations may not hold.

## Standard Sample Size Calculation

Using the standard formula for comparing two means:

$$n = 2 \times \frac{(z_{\alpha/2} + z_{\beta})^2 \times \sigma^2}{(MDE)^2}$$

Where:
- z₀.₀₂₅ = 1.96 (95% confidence, two-tailed)
- z₀.₂₀ = 0.84 (80% power)
- σ = $60
- MDE = $3

$$n = 2 \times \frac{(1.96 + 0.84)^2 \times 60^2}{3^2}$$

$$n = 2 \times \frac{(2.80)^2 \times 3600}{9}$$

$$n = 2 \times \frac{7.84 \times 3600}{9}$$

$$n = 2 \times 3,141.33 = \mathbf{6,272 \text{ users per group}}$$

**Total sample size: 12,544 users**

## Practical Timeline

With 8,000 eligible users per week and a 50/50 split (4,000 per group per week), you would need approximately **1.6 weeks** to reach the required sample size.

## Important Caveats and Recommendations

### 1. Unreliable Estimate Due to High Variance

The CV of 3.0 is well above typical thresholds. The standard normal-based formula assumes symmetric distributions and may underestimate the true sample size needed. Real revenue data with this level of variance is likely heavily right-skewed, violating the normality assumption.

### 2. Recommend Data Transformation or Capping

Before running the experiment, consider:

- **Winsorize or cap outliers:** Consider capping extremely high individual transactions (e.g., at the 95th or 99th percentile). This is common practice in revenue analysis and can stabilize variance estimates.
- **Log-transformation:** Alternatively, analyze log(revenue) instead of raw revenue, which can reduce skewness and normalize the distribution.
- **Quantile metrics:** Consider using median revenue or revenue at specific quantiles instead of mean, which are more robust to outliers.

### 3. Validate Baseline SD from Historical Data

The standard deviation of $60 should be verified against recent historical data from your monetization flow. If this figure comes from a limited sample or outdated period, the actual SD could differ significantly, which would invalidate the sample size estimate. Confirm this is the current, representative standard deviation before committing to your experimental timeline.

### 4. Consider Power Analysis Robustness

If your actual revenue distribution is log-normal rather than normal, the power of your test may be different from the 80% calculated here. Running a simulation with historical revenue data would provide more confidence in the estimated power.

### 5. Plan for Sequential Monitoring

Given the high variance, consider implementing a sequential analysis or optional stopping rules with adjusted p-values to allow earlier stopping if a clear effect emerges.

## Summary

**Plan for approximately 6,300 users per group (12,600 total), achievable in ~1.6 weeks.** However, given the extremely high variance (CV=3.0) in revenue data, strongly recommend:
1. Reviewing your data distribution assumptions (histogram/Q-Q plot)
2. Applying outlier capping or log-transformation before finalizing the experiment design
3. Validating the $60 baseline SD against current historical data
4. Running a simulation to verify power under your actual revenue distribution
