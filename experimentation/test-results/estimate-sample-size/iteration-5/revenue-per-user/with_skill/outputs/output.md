# Sample Size Estimate: Monetisation Flow A/B Test

## Inputs Provided

| Parameter | Value |
|-----------|-------|
| Primary metric | Average Revenue Per User (ARPU) |
| Baseline mean | $20 |
| Baseline standard deviation | $60 |
| Minimum detectable effect (MDE) | +$3 (absolute) |
| Confidence level | 95% |
| Power | 80% |
| Eligible traffic | 8,000 users/week |
| Split ratio | 50/50 |

## Key Finding: High-Variance Metric

**Coefficient of Variation (CV) = $60 / $20 = 3.0**

This is a **highly right-skewed, high-variance metric**. A CV of 3.0 is well above the threshold of 1.0 and indicates severe skew — typical for revenue metrics where a small number of high-value users pull the mean significantly higher than the median. The standard sample size formula significantly **underestimates** the required sample size for such skewed distributions.

## Sample Size Estimate

### Approach 1: Standard Continuous Formula (Conservative Lower Bound)
```
n_per_group = (1.96 + 0.84)² × 2 × σ² / δ²
n_per_group = 7.84 × 2 × 60² / 3²
n_per_group = 7.84 × 2 × 3,600 / 9
n_per_group = 7.84 × 800
n_per_group ≈ 6,272 users per group
```

**Total sample size: 12,544 users**

### Approach 2: Log-Normal Formula (Recommended for CV ≥ 1)
For a metric this skewed, the log-normal approach is more appropriate:

```
σ_log = √(ln(1 + CV²)) = √(ln(1 + 9)) = √(ln(10)) = √2.303 ≈ 1.517
δ_log = ln(1 + δ_abs / μ_baseline) = ln(1 + 3/20) = ln(1.15) ≈ 0.1398
n_per_group = 7.84 × 2 × σ_log² / δ_log²
n_per_group = 7.84 × 2 × 2.302 / 0.0195
n_per_group ≈ 1,848 users per group
```

**Total sample size: 3,696 users**

## Critical Caveat: Sample Size Reliability

**⚠️ Warning:** Both estimates are sensitive to the variance assumption and the assumed distribution shape. The log-normal estimate (1,848/group) is preferred but assumes the underlying distribution behaves log-normally. The standard formula (6,272/group) is more conservative but may still underestimate if the true SD is higher or the distribution is more extreme than typical.

**Do not rely on either estimate until historical SD is validated.** Before committing to a timeline, ensure that:
1. The $60 SD reflects the actual distribution of recent ARPU data, not an outlier period
2. The distribution shape (log-normal vs. other) is confirmed from recent historical samples
3. You have at least 30–50 days of recent baseline data to validate the assumption

## Recommended Approach: Outlier Capping

**We strongly recommend capping outliers at the 99th percentile before running or analyzing this experiment.** This approach:
- Reduces effective variance without losing material signal
- Makes the experiment feasible without inflating sample size unnaturally
- Preserves detection ability for typical user segments
- Is standard practice for monetisation experiments with high skew

With outlier capping (99th percentile), the effective SD will be meaningfully lower, reducing the required sample size to a more practical level. For example, if capping reduces SD from $60 to $40 (realistic for many monetisation metrics), the log-normal n would drop from 1,848 to around 800/group.

## Estimated Duration

Using the log-normal estimate (3,696 total) and eligible traffic of 8,000 users/week:

```
duration = 3,696 / 8,000 ≈ 0.46 weeks ≈ 3.2 days
```

Using the standard formula estimate (12,544 total):

```
duration = 12,544 / 8,000 ≈ 1.57 weeks ≈ 11 days
```

**Note:** These durations assume steady eligible traffic throughout the test period. Validate that 8,000 users/week is truly the eligible traffic (users who reach the upsell prompt step), not total product traffic. If traffic is seasonal or variable, actual duration may differ.

## Assumptions Used

1. **Baseline parameters** ($20 mean, $60 SD) are validated from recent historical data
2. **Confidence and power** are conventional: 95% (two-sided) and 80% power
3. **MDE of +$3** represents a 15% relative uplift, which is material for monetisation
4. **Eligible traffic of 8,000/week** reaches the upsell prompt and is stable over the test period
5. **50/50 split** means equal assignment to control and treatment
6. **No external confounders** (seasonality, marketing campaigns, major platform changes) during the test window

## Feasibility Summary

| Scenario | Sample/Group | Total Sample | Duration |
|----------|--------------|--------------|----------|
| Log-normal (primary) | 1,848 | 3,696 | ~3 days |
| Standard formula | 6,272 | 12,544 | ~11 days |
| With 99th-percentile capping | ~800 | ~1,600 | ~1 day |

**Recommendation:** Given the high skew and your eligible traffic, the experiment is **feasible**. However:
- Run validation on the baseline SD before locking the timeline
- Implement outlier capping before analysis to ensure result interpretability
- If possible, run a pilot or use historical A/A test data to confirm the effective variance under your capping strategy
