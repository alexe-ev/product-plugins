# A/B Test Sample Size Estimation
## Food Delivery App - Restaurant Card Design Test

### Test Objective
Estimate the required sample size to detect a +0.8 percentage point increase in click-to-order conversion rate at 95% confidence and 80% statistical power.

---

## Input Parameters

| Parameter | Value |
|-----------|-------|
| **Primary Metric** | Click-to-order conversion rate |
| **Baseline Conversion Rate** | 7.8% |
| **Minimum Detectable Effect (MDE)** | +0.8 percentage points (absolute) |
| **Target Conversion Rate** | 8.6% (7.8% + 0.8pp) |
| **Confidence Level** | 95% (α = 0.05, two-tailed) |
| **Statistical Power** | 80% (1 - β = 0.80) |
| **Test Split** | 50/50 (equal allocation) |
| **Weekly Eligible Traffic** | 35,000 users |

---

## Calculation Details

### Step 1: Critical Values
- **Z-score for 95% confidence (two-tailed):** z_α/2 = 1.96
- **Z-score for 80% power:** z_β = 0.84

### Step 2: Pooled Proportion
- p̄ = (p₀ + p₁) / 2
- p̄ = (0.078 + 0.086) / 2
- **p̄ = 0.082**

### Step 3: Variance Components
- p₀(1 - p₀) = 0.078 × 0.922 = 0.071916
- p₁(1 - p₁) = 0.086 × 0.914 = 0.078604
- **Sum of variances = 0.15052**

### Step 4: Effect Size
- (p₁ - p₀)² = (0.086 - 0.078)²
- (p₁ - p₀)² = (0.008)²
- **(p₁ - p₀)² = 0.000064**

### Step 5: Sample Size Formula
Using the two-proportion hypothesis test formula:

```
n = [(z_α/2 + z_β)² × (p₀(1 - p₀) + p₁(1 - p₁))] / (p₁ - p₀)²
```

Substituting values:
```
n = [(1.96 + 0.84)² × 0.15052] / 0.000064
n = [(2.80)² × 0.15052] / 0.000064
n = [7.84 × 0.15052] / 0.000064
n = 1.17968 / 0.000064
n = 18,433.75
```

**Sample size per group: 18,434** (rounded up)

---

## Results Summary

| Metric | Value |
|--------|-------|
| **Sample Size Per Group** | 18,434 |
| **Total Sample Size** | 36,868 |
| **Traffic Required Per Week** | 35,000 |
| **Test Duration** | ~1.05 weeks (7-8 days) |
| **% of Weekly Traffic** | 105.3% |

### Key Findings

1. **Sample Size:** You need 18,434 users in each group (control and treatment) to reliably detect a +0.8 percentage point difference in click-to-order conversion rate.

2. **Total Traffic Required:** 36,868 users total (both groups combined).

3. **Test Duration:** With 35,000 weekly eligible users, you'll need approximately 1.05 weeks (~7-8 days) to reach the required sample size.

4. **Power Analysis:** At this sample size, you have:
   - 95% confidence that you won't incorrectly reject the null hypothesis (Type I error ≤ 5%)
   - 80% power to detect the +0.8pp effect if it truly exists (Type II error ≤ 20%)

---

## Recommendations

- **Test Duration:** Plan for 8-10 days to account for traffic variation and ensure you reach the target sample size.
- **Monitoring:** Use sequential testing or fixed sample size approach depending on your testing infrastructure.
- **Practical Significance:** Even if the test is statistically significant, the +0.8pp improvement represents approximately a 10.3% relative uplift in conversion (0.8 / 7.8), which is practically meaningful for a food delivery platform.
- **Multiple Comparisons:** If testing multiple metrics simultaneously, consider adjusting the confidence level using Bonferroni correction or similar methods.

---

## Methodology Notes

- **Formula Used:** Two-proportion hypothesis test with equal sample allocation
- **Distribution:** Normal approximation to the binomial distribution
- **Assumptions:**
  - Samples are independent
  - Baseline conversion rate is stable during test period
  - No network effects or user interference
  - Users are randomly assigned to control/treatment groups
