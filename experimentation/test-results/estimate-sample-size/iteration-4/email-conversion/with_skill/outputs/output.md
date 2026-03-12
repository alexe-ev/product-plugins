# Sample Size Estimation: Email Open Rate A/B Test

## Input Summary
Primary metric: email open rate (conversion)
Baseline: 22%
Minimum detectable effect: +2 percentage points
Confidence level: 95%
Power: 80%
Eligible traffic: 8,000 emails per week
Split: 50/50

## Calculation

### Formula (Conversion Metric)
```
n_per_group = (z_α/2 + z_β)² × (p1×(1−p1) + p2×(1−p2)) / (p2 − p1)²
```

### Step-by-Step Calculation

**Step 1: Define z-values**
- z_α/2 (95% confidence, two-sided) = 1.96
- z_β (80% power) = 0.84
- (z_α/2 + z_β)² = (1.96 + 0.84)² = (2.80)² = 7.84

**Step 2: Define conversion rates**
- p1 (baseline) = 0.22
- p2 (target) = 0.22 + 0.02 = 0.24

**Step 3: Calculate variance term**
- p1×(1−p1) = 0.22 × 0.78 = 0.1716
- p2×(1−p2) = 0.24 × 0.76 = 0.1824
- Sum = 0.1716 + 0.1824 = 0.3540

**Step 4: Calculate effect size squared**
- (p2 − p1)² = (0.24 − 0.22)² = (0.02)² = 0.0004

**Step 5: Calculate sample size per group**
- Numerator: 7.84 × 0.3540 = 2.77056
- n_per_group = 2.77056 / 0.0004 = 6,926.4 ≈ **6,926 users per group**

**Step 6: Calculate total sample size**
- Total = 6,926 × 2 = **13,852 users**

**Step 7: Calculate estimated duration**
- Duration = 13,852 / 8,000 = 1.73 weeks ≈ **1.7 weeks**

## Results

**Sample size per group:** 6,926 users

**Total sample size:** 13,852 users

**Estimated duration:** Approximately 1.7 weeks of eligible traffic

## Inputs Used
- Conversion metric (email open rate)
- Baseline 22%
- Target 24%
- Confidence 95%
- Power 80%
- Even 50/50 split
- 8,000 eligible emails per week

## Assumptions
- Two-variant fixed-horizon A/B test
- Stable email delivery and engagement across the test period
- No major distortion from campaign timing, seasonal effects, or audience shifts
- Eligible traffic refers to all weekly digest emails sent in the test window
- Email opens are independent and follow a binomial distribution

## Feasibility Assessment

**Status:** Highly feasible

This is an excellent experiment setup. The required sample size of ~13,852 emails can be collected in less than 2 weeks from your eligible traffic of 8,000 emails per week. This short duration:
- Minimizes exposure to confounding factors
- Allows rapid iteration on subject line formats
- Maintains statistical rigor without excessive runtime

**Considerations:**
- Ensure the 8,000/week baseline is stable and not inflated by seasonal campaigns
- If the baseline varies week-to-week, allow an extra week as buffer
- Consider whether subject line variants might have delayed-open effects beyond the standard measurement window
