# Sample Size Calculation for 30-Day Retention Experiment

## Given Parameters
- Baseline retention: 42%
- Minimum detectable effect: +3 percentage points (45% target)
- Confidence level: 95% (α = 0.05, two-tailed)
- Power: 80% (β = 0.20)
- Split: 50/50
- Cohort dilution: 15%
- New user acquisition: 5,000 users/week

## Effective Sample Size Calculation

For a two-proportion test, the required sample size per group using standard formulas:

n = 2 × [(z_α/2 + z_β)² × p(1-p)] / (effect_size)²

Where:
- z_α/2 = 1.96 (95% confidence)
- z_β = 0.84 (80% power)
- p = average of baseline and target = (0.42 + 0.45) / 2 = 0.435
- effect_size = 0.03

**Calculation:**
- n ≈ 2 × [(1.96 + 0.84)² × 0.435 × 0.565] / (0.03)²
- n ≈ 2 × [7.84 × 0.246] / 0.0009
- n ≈ 2 × 2,139 ≈ **4,278 per group (effective sample)**

## Adjusting for Cohort Dilution

With 15% dilution, we need to increase our sample size to account for those who will become unmeasurable:

- Dilution factor = 1 / (1 - 0.15) = 1 / 0.85 = 1.176
- **Enrolled per group = 4,278 × 1.176 ≈ 5,035 per group**
- **Total enrolled = 2 × 5,035 ≈ 10,070 users**

## Duration Estimate

At 5,000 new users per week:
- **Duration = 10,070 / 5,000 ≈ 2.01 weeks**

## Important Note on Eligible Traffic

When designing a retention experiment, "eligible traffic" refers specifically to new users being enrolled into the cohort, not the total active user base. This is critical because retention is measured from the cohort entry point. Only users who enter the experiment during the test period are part of the sample and contribute to the retention measurement.

## Summary

| Metric | Value |
|--------|-------|
| Effective sample per group | 4,278 |
| Enrolled sample per group | 5,035 |
| Total enrolled sample | 10,070 |
| Expected test duration | 2.01 weeks |
