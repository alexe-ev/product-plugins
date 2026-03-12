# Sample Size Calculation for Checkout Form Redesign Test

## Input Parameters
- **Primary Metric**: Form completion rate (conversion)
- **Baseline (p₁)**: 34% = 0.34
- **Minimum Detectable Effect (MDE)**: +4 percentage points
- **Effect Size (p₂)**: 0.34 + 0.04 = 0.38
- **Confidence Level (α)**: 95% (two-tailed)
- **Statistical Power (1-β)**: 90%
- **Eligible Traffic**: 5,500 users per week
- **Traffic Split**: 50/50 (equal allocation)

## Critical Z-Values
- **z_alpha (two-tailed, 95% confidence)**: 1.96
- **z_beta (one-tailed, 90% power)**: 1.28

## Formulas

### Standard Error Calculation
For comparing two proportions:

$$SE = \sqrt{p_1(1-p_1) + p_2(1-p_2)}$$

Where:
- p₁ = baseline conversion rate = 0.34
- p₂ = expected conversion rate = 0.38

### Sample Size Formula
For equal allocation (n per group):

$$n = \frac{(z_\alpha + z_\beta)^2 \times (p_1(1-p_1) + p_2(1-p_2))}{(p_2 - p_1)^2}$$

## Step-by-Step Calculation

### Step 1: Calculate pooled proportions
- p₁(1-p₁) = 0.34 × 0.66 = 0.2244
- p₂(1-p₂) = 0.38 × 0.62 = 0.2356
- Sum = 0.2244 + 0.2356 = 0.4600

### Step 2: Calculate z-score sum
- z_alpha + z_beta = 1.96 + 1.28 = 3.24

### Step 3: Calculate (z_alpha + z_beta)²
- 3.24² = 10.4976

### Step 4: Calculate effect size squared
- (p₂ - p₁)² = (0.38 - 0.34)² = 0.04² = 0.0016

### Step 5: Calculate numerator
- (z_alpha + z_beta)² × (p₁(1-p₁) + p₂(1-p₂))
- 10.4976 × 0.4600 = 4.8289

### Step 6: Calculate sample size per group
- n = 4.8289 / 0.0016 = **3,018 per group**

## Sample Size Summary

| Metric | Value |
|--------|-------|
| **Sample size per group (n)** | 3,018 |
| **Total sample size (2n)** | 6,036 |
| **Traffic allocation - Control** | 50% → 3,018 users |
| **Traffic allocation - Treatment** | 50% → 3,018 users |

## Test Duration

**Weekly eligible traffic**: 5,500 users per week

- **Users needed per week (one group)**: 3,018 / 5,500 = 0.549 weeks
- **Minimum duration (both groups)**: 0.549 weeks ≈ **3.8 days**
- **Recommended duration**: 1-2 weeks (to account for day-of-week effects and external variation)

## Power Analysis Verification

With n = 3,018 per group:
- Detects a 4 percentage point increase from 34% to 38% baseline
- At 95% confidence level (α = 0.05, two-tailed)
- With 90% power (β = 0.10, Type II error rate 10%)
- Probability of detecting true effect if it exists: 90%
- Probability of false positive if null is true: 5%

## Interpretation

**The test requires 3,018 users in each group (control and treatment)** for a total of 6,036 users to reliably detect a 4 percentage point improvement in form completion rate.

Given 5,500 eligible users per week:
- Collecting full sample will take approximately **5-6 days** of traffic
- Running for **1-2 weeks is recommended** for seasonal robustness and confidence in stability of treatment effect

## Statistical Validity

This sample size calculation ensures:
✓ 95% confidence that observed difference is not due to chance (if p-value < 0.05)
✓ 90% probability of detecting the 4pp effect if it truly exists
✓ Balanced Type I (5%) and Type II (10%) error rates appropriate for product decisions
