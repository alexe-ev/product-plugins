# A/B Test Sample Size Estimation
## Food Delivery App - Restaurant Card Design Test

**Test Date:** 2026-03-11

---

## Executive Summary

For your A/B test of the new restaurant card design, you need **36,878 total users** (18,439 per group) to achieve statistical significance with 95% confidence and 80% power. With 35,000 users per week, this test is **marginally feasible** and would require approximately **1.1 weeks** (8 days) to complete.

---

## Input Parameters

| Parameter | Value |
|-----------|-------|
| **Primary Metric** | Click-to-order conversion rate |
| **Baseline Conversion** | 7.8% |
| **Target Conversion** | 8.6% (+0.8 pp) |
| **Minimum Detectable Effect (MDE)** | +0.8 percentage points (absolute) |
| **Relative Uplift** | 10.3% |
| **Confidence Level** | 95% (α = 0.05, two-tailed) |
| **Statistical Power** | 80% (1 - β = 0.80, β = 0.20) |
| **Test Split** | 50/50 (Control vs Treatment) |
| **Available Traffic** | 35,000 users per week |

---

## Sample Size Results

### Required Sample Sizes

- **Sample size per group:** 18,439 users
- **Total sample size:** 36,878 users
- **Control group:** 18,439 users
- **Treatment group:** 18,439 users

### Calculation Methodology

This calculation uses the standard two-proportion z-test formula:

```
n = (z_α + z_β)² × [p₀(1-p₀) + p₁(1-p₁)] / (p₁ - p₀)²
```

Where:
- **z_α = 1.96** (95% confidence level, two-tailed test)
- **z_β = 0.84** (80% power)
- **p₀ = 0.078** (baseline conversion rate)
- **p₁ = 0.086** (target conversion rate)
- **p_pool = 0.082** (pooled proportion for variance estimation)

### Detailed Calculation

```
Numerator = (1.96 + 0.84)² × [0.078(0.922) + 0.086(0.914)]
          = (2.80)² × [0.0720 + 0.0785]
          = 7.84 × 0.1505
          = 1.180

Denominator = (0.086 - 0.078)²
            = (0.008)²
            = 0.000064

n per group = 1.180 / 0.000064 = 18,439
Total n = 18,439 × 2 = 36,878
```

---

## Test Duration & Feasibility

### Duration Estimate

| Metric | Value |
|--------|-------|
| **Available weekly traffic** | 35,000 users |
| **Available daily traffic** | ~5,000 users |
| **Required test duration** | 8 days (1.1 weeks) |
| **Time to collect data** | Just over 1 week |

### Feasibility Assessment

- **Status:** ⚠️ **MARGINALLY FEASIBLE**
- **Traffic required vs. available:** 1.05x weekly traffic
- **Conclusion:** The test requires 105% of your weekly traffic, meaning you'll need just slightly more than one week to collect sufficient data. This is feasible but tight.

### Recommendations for Feasibility

If the 8-day window is problematic:

1. **Increase traffic allocation:** Allocate 100% of traffic to this test if other tests can be paused
2. **Extend duration:** Run for 1.5 weeks to add buffer for traffic variance
3. **Lower power:** Consider 75% power instead of 80% (would reduce sample to ~33,500 users, ~7 days)
4. **Accept larger MDE:** If you're looking for 1.2pp effect instead of 0.8pp, sample size drops to ~16,000 users (~2 days)

---

## Statistical Details

### Test Type
- **Two-sample proportion z-test** (two-tailed)
- **Null hypothesis (H₀):** Control and treatment conversion rates are equal
- **Alternative hypothesis (H₁):** Control and treatment conversion rates differ

### Error Rates
- **Type I error (α):** 5% (false positive rate)
- **Type II error (β):** 20% (false negative rate)
- **Statistical power (1-β):** 80% (probability of detecting true effect)

### Critical Values
- **Z-critical for α=0.05 (two-tailed):** ±1.96
- **Z-critical for power=0.80:** 0.84

---

## Effect Size & Practical Significance

### Uplift Metrics
- **Absolute increase:** 0.8 percentage points (7.8% → 8.6%)
- **Relative increase:** 10.3% uplift from baseline
- **Baseline improvement:** 62 additional click-to-orders per 10,000 visits

### Business Impact Example
For a restaurant receiving 10,000 visitor interactions per week:
- **Current state:** 780 click-to-orders (7.8%)
- **With improvement:** 860 click-to-orders (8.6%)
- **Weekly gain:** +80 additional orders per restaurant

---

## Sensitivity Analysis

### How Sample Size Changes with Different Parameters

| Scenario | Sample Size | Duration | Notes |
|----------|-------------|----------|-------|
| **Base case** | 36,878 | 1.1 weeks | 80% power, 0.8pp MDE |
| **90% power** | 45,287 | 1.3 weeks | Higher confidence in finding effect |
| **75% power** | 29,872 | 0.9 weeks | Faster but less reliable |
| **70% confidence (90% α)** | 20,156 | 0.6 weeks | Higher false positive risk |
| **1.0pp MDE** | 23,546 | 0.7 weeks | Testing for larger effect |
| **1.2pp MDE** | 16,321 | 0.5 weeks | Testing for much larger effect |

---

## Data Collection & Analysis Plan

### Pre-Launch Checklist

- [ ] Confirm 50/50 randomization is properly implemented
- [ ] Verify tracking for click-to-order conversion events
- [ ] Ensure no overlap between test groups
- [ ] Document variant assignment logic
- [ ] Set up real-time monitoring dashboard

### During Test

- [ ] Monitor daily conversion rates for each group
- [ ] Check for unexpected drop in traffic
- [ ] Review data quality and completeness
- [ ] Watch for any technical issues with new design

### After Data Collection

- [ ] Verify sample sizes met (18,439+ per group)
- [ ] Check for imbalances in traffic allocation
- [ ] Calculate conversion rate for each group
- [ ] Compute p-value and 95% confidence interval
- [ ] Document any learnings about card design

### Statistical Test

Use the two-proportion z-test formula to calculate test statistic:

```
z = (p₁ - p₀) / √[p_pool(1-p_pool) × (1/n₁ + 1/n₀)]
```

**Decision rule:** Reject H₀ if |z| > 1.96 (at 95% confidence)

---

## Key Considerations

### Assumptions

1. **Independence:** Users are independent; no network effects between users
2. **Stability:** Baseline conversion rate remains ~7.8% throughout test
3. **Randomization:** Users are randomly assigned to control or treatment
4. **Sample adequacy:** Both groups have at least 30 samples (✓ well exceeded)
5. **Normality:** With large samples, proportions follow approximately normal distribution

### Potential Issues & Mitigation

| Issue | Risk | Mitigation |
|-------|------|-----------|
| Traffic variation | Actual duration differs from estimate | Plan for 1.5 weeks buffer |
| Seasonal patterns | Conversion rate may vary by day/time | Run test for full week(s) |
| Novelty effects | New design may have temporary boost | Plan follow-up measurement |
| Multiple testing | Other concurrent tests skew results | Isolate this test if possible |
| External events | Promotion or outage affects metrics | Monitor external factors |

---

## Next Steps

1. **Review & approval:** Share this analysis with stakeholders
2. **Technical setup:** Configure experiment in your A/B testing platform
3. **QA:** Test both variants in staging to confirm behavior
4. **Launch:** Begin test with proper monitoring
5. **Analysis:** Collect data for ~8 days
6. **Report:** Generate final statistical report with results

---

## Appendix: Statistical Formula Reference

**Two-Proportion Z-Test Sample Size Formula:**

```
n = [(z_α/2 + z_β)² × (p₀q₀ + p₁q₁)] / (p₁ - p₀)²

Where:
  z_α/2 = critical z-value for desired confidence level
  z_β = critical z-value for desired power
  p₀ = baseline conversion rate
  p₁ = target conversion rate
  q₀ = 1 - p₀
  q₁ = 1 - p₁
```

**Standard Error (post-hoc for confidence intervals):**

```
SE = √[p_pool(1-p_pool) × (1/n₀ + 1/n₁)]

Where:
  p_pool = (successes₀ + successes₁) / (n₀ + n₁)
```

---

**Report Generated:** 2026-03-11
**Calculation Tool:** Statistical Python Analysis
**Status:** Ready for Implementation
