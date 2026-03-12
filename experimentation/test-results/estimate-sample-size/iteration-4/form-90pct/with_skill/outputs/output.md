# Sample Size Estimation: Redesigned Checkout Form

## Input Summary
Primary metric: form completion rate (conversion)
Baseline: 34%
Minimum detectable effect: +4 percentage points
Confidence level: 95%
Power: 90%
Eligible traffic: 5,500 users per week
Split: 50/50

## Calculation

### Conversion Metric Formula
Using the explicit formula for conversion/rate metrics:

```
n_per_group = (z_α/2 + z_β)² × (p1×(1−p1) + p2×(1−p2)) / (p2 − p1)²
```

### Step 1: Z-values
- Confidence level: 95% (two-sided) → z_α/2 = 1.96
- Power: 90% → z_β = 1.28
- Sum: z_α/2 + z_β = 1.96 + 1.28 = 3.24
- Squared: (3.24)² = 10.4976

### Step 2: Effect Size
- Baseline conversion (p1): 34% = 0.34
- Target conversion (p2): 34% + 4% = 38% = 0.38
- Effect: (p2 − p1) = 0.04
- Effect squared: (0.04)² = 0.0016

### Step 3: Variance Term
- p1×(1−p1) = 0.34 × 0.66 = 0.2244
- p2×(1−p2) = 0.38 × 0.62 = 0.2356
- Sum: 0.2244 + 0.2356 = 0.4600

### Step 4: Sample Size Per Group
```
n_per_group = 10.4976 × 0.4600 / 0.0016
n_per_group = 4.8290 / 0.0016
n_per_group ≈ 3,018 users
```

### Step 5: Total Sample Size
```
Total = 3,018 × 2 (control and treatment)
Total ≈ 6,036 users
```

### Step 6: Estimated Duration
```
Duration = Total required sample / Eligible traffic per week
Duration = 6,036 / 5,500
Duration ≈ 1.10 weeks (approximately 1 week and 1 day)
```

## Results

**Sample size per group:** ~3,018 users
**Total sample size:** ~6,036 users
**Estimated duration:** ~1.1 weeks

## Inputs Used
- Conversion metric (form completion)
- Baseline: 34%
- Target: 38% (baseline + 4pp MDE)
- Confidence: 95% (z_α/2 = 1.96)
- Power: 90% (z_β = 1.28)
- Even split (50/50 control/treatment)
- 5,500 eligible users per week

## Assumptions
- Two-variant fixed-horizon A/B test
- Stable form completion baseline across test period
- Eligible traffic remains stable during test window
- No major distortion from promotions, seasonal effects, or traffic source shifts
- Eligible traffic refers to users who actually reach and interact with the checkout form
- Form interaction patterns consistent across test variants

## Feasibility Assessment
**Status: Feasible and practical**

This test is highly feasible:
- Required sample (6,036) is modest relative to weekly traffic (5,500)
- Estimated duration (1.1 weeks) is short, allowing rapid validation
- Effect size (4 percentage points on 34% baseline = 11.8% relative uplift) is substantial and detectable
- With 90% power and 95% confidence, the test has strong statistical precision

## Caveats
- Duration estimate assumes consistent weekly traffic of 5,500 eligible users
- If traffic is lower than 5,500/week, duration will extend accordingly
- If traffic varies significantly week-to-week, account for variability in planning
- No adjustment made for multiple comparisons or secondary metrics
- Result assumes form completion can be measured cleanly at the point of interest
