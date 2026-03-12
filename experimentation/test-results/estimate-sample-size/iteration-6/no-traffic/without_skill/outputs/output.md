# Sample Size Estimate for Pricing Page Redesign Test

## Test Parameters
- **Primary Metric**: Purchase conversion rate
- **Baseline Conversion**: 3.2%
- **Minimum Detectable Effect**: +0.4 percentage points
- **Target Conversion**: 3.6%
- **Confidence Level**: 95%
- **Statistical Power**: 80%

## Sample Size Calculation

Using two-proportion hypothesis testing with:
- Z_α/2 = 1.96 (95% confidence, two-tailed)
- Z_β = 0.84 (80% power)

**Formula**: n = (Z_α/2 + Z_β)² × [p₁(1-p₁) + p₂(1-p₂)] / (p₂ - p₁)²

**Calculation**:
- n = (1.96 + 0.84)² × [0.032(0.968) + 0.036(0.964)] / (0.004)²
- n = 7.84 × 0.06568 / 0.000016
- n ≈ **32,000 per group**

## Results

| Metric | Value |
|--------|-------|
| **Sample size per group** | 32,000 |
| **Total sample size** | 64,000 |
| **Control group** | 32,000 |
| **Treatment group** | 32,000 |

## Timeline Estimation

**Cannot be determined at this time** — you have not provided your eligible traffic volume.

To estimate when you'll have results, I need to know: **How many eligible users visit your pricing page per week (or per relevant time period)?**

Once you provide this traffic metric, I can calculate the expected test duration by dividing the total sample size by your weekly traffic volume.
