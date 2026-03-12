# Sample Size Estimate: Three-Variant Checkout Test

## Test Setup
- **Variants**: 3 total (1 control + 2 treatments)
- **Control**: 12% conversion rate
- **Variant A & B**: 13.5% conversion rate (target)
- **Absolute uplift**: +1.5 percentage points
- **Family-wise confidence**: 95%
- **Power per comparison**: 80%
- **Eligible traffic**: 6,000 users/week
- **Split**: Equal thirds

## Statistical Correction for Multiple Comparisons

This is a **multi-variant test with K=2 treatment comparisons** against the control. To maintain 95% family-wise error rate across both treatment arms, I apply **Bonferroni correction**:

- α_family = 0.05 (95% confidence)
- K = 2 (number of treatment arms)
- α_per_comparison = 0.05 / 2 = 0.025
- **z_adj = 2.24** (two-tailed z-value for α = 0.025)
- z_β = 0.84 (80% power)
- **(z_adj + z_β)² = (2.24 + 0.84)² = 9.49**

## Sample Size Calculation

Using the conversion metric formula with adjusted critical value:

```
n_per_arm = (z_adj + z_β)² × (p1×(1−p1) + p2×(1−p2)) / (p2 − p1)²
```

**Inputs:**
- p1 = 0.12 (baseline control conversion)
- p2 = 0.135 (target conversion)
- (p2 − p1) = 0.015

**Calculation:**
- Variance term: 0.12 × 0.88 + 0.135 × 0.865 = 0.1056 + 0.1168 = 0.2224
- Numerator: 9.49 × 0.2224 = 2.109
- Denominator: (0.015)² = 0.000225
- **n_per_arm = 2.109 / 0.000225 ≈ 9,373 users**

**Total sample size = 9,373 × 3 = 28,119 users** (all three arms)

## Duration Estimate

With 6,000 eligible users per week and equal split across three arms:

```
duration = total_sample / eligible_traffic_per_period
duration = 28,119 / 6,000 ≈ 4.7 weeks
```

## Comparison to Standard Two-Variant Test

For context, a standard two-variant test (no correction, K=1) with the same inputs would require:
- z-value: (1.96 + 0.84)² = 7.84
- n_per_arm ≈ 7.84 × 0.2224 / 0.000225 ≈ 7,750 users
- Total ≈ 15,500 users, or ~2.6 weeks

**The Bonferroni correction increases the per-arm sample size by approximately 21%** (9,373 vs 7,750), and the addition of a third arm brings the total sample to 28,119 instead of 15,500—**making the multi-variant test 81% larger in total sample and 1.8× longer in expected duration**. This is the cost of testing two treatments simultaneously while controlling family-wise false positive rate.

## Assumptions

1. Baseline 12% conversion rate is accurate.
2. Both treatment arms are equally likely to achieve +1.5pp uplift.
3. No substantial difference in variance structure between control and treatment.
4. Traffic is stable across the test window (no seasonality, acquisition changes, or campaign effects).
5. Conversion events are observed within a single session (no delayed attribution).
6. Equal traffic split (1/3 per arm) is feasible operationally.

## Feasibility

✓ **Feasible**: 4.7-week duration is reasonable for checkout optimization. Traffic capacity is sufficient. The uplift target of +1.5pp is material enough to be business-meaningful and statistically achievable in the timeframe.
