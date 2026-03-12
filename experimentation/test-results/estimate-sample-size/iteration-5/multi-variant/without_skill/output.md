# Sample Size Calculation: Three-Variant Checkout Test

## Problem Statement
Three-variant test on checkout page:
- **Control**: Current checkout (12% conversion rate)
- **Variant A**: Simplified one-page checkout (target: 13.5%)
- **Variant B**: Split-step checkout (target: 13.5%)
- **Family-wise confidence**: 95%
- **Power per comparison**: 80%
- **Eligible traffic**: 6,000 users/week with equal thirds split

## Statistical Framework

### Multiple Comparison Correction
- Number of treatment comparisons: K = 2 (Variant A vs Control, Variant B vs Control)
- Bonferroni-corrected α per comparison: α_per = 0.05/2 = **0.025**
- Critical z-value for α = 0.025 (one-tailed): z_α = 1.96
- Critical z-value for β = 0.20 (80% power): z_β = 0.84
- Adjusted z-critical with Bonferroni correction: z_adj ≈ **2.24**

### Effect Size Parameters
- Baseline conversion rate: p₀ = 12% = 0.12
- Target conversion rate: p₁ = 13.5% = 0.135
- Absolute effect size: Δp = 1.5 percentage points
- Relative lift: 12.5%

## Sample Size Calculation

Using the two-proportion z-test formula with Bonferroni adjustment:

n = 2 × [(z_α + z_β)² × (p₀(1-p₀) + p₁(1-p₁))] / (p₁ - p₀)²

Substituting values:
- n = 2 × [(2.24 + 0.84)² × (0.12×0.88 + 0.135×0.865)] / (0.015)²
- n = 2 × [9.36 × 0.2019] / 0.000225
- n ≈ **9,250 per arm**

### Results
- **Sample size per arm**: 9,250 users
- **Total sample size**: 3 arms × 9,250 = **27,750 users**
- **Duration**: 27,750 / 6,000 users per week ≈ **4.6 weeks**

## Comparison to Standard Two-Variant Test

A standard two-variant test (1 control + 1 treatment) with identical parameters (α = 0.05, 80% power) would require approximately 7,700 users per arm (23,100 total).

**Impact of Bonferroni Correction**: The per-arm sample size increases by roughly 20% (from ~7,700 to ~9,250) due to the multiple-comparison correction. This is necessary to maintain the family-wise error rate of 95% across both treatment comparisons.

## Timeline
- **Sample size needed**: 27,750 users
- **Weekly eligible traffic**: 6,000 users
- **Estimated duration**: **4.6 weeks** (approximately 4–5 weeks in practice)
