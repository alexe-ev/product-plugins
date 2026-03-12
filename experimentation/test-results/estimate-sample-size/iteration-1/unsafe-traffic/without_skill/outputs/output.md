# Sample Size Calculation for B2B Onboarding Wizard A/B Test

## Test Specifications
- **Primary Metric**: Onboarding completion rate
- **Baseline Completion Rate**: 41%
- **Minimum Detectable Effect (MDE)**: +5 percentage points (target: 46%)
- **Confidence Level**: 95% (α = 0.05)
- **Statistical Power**: 80% (β = 0.20, 1-β = 0.80)
- **Test Type**: Two-tailed test

## Population Context
- **Total Registered Users**: 25,000
- **New Sign-ups Rate**: 15% per month
- **Eligible Users per Month**: 3,750 users/month (25,000 × 0.15)

## Statistical Calculation

### Method: Proportions Test (Two-Sample)

Using the standard formula for comparing two proportions:

```
n = 2 × [Z_{α/2} + Z_β]² × [p₁(1-p₁) + p₂(1-p₂)] / (p₁ - p₂)²
```

Where:
- **p₁** (Control): 0.41 (baseline completion rate)
- **p₂** (Treatment): 0.46 (baseline + MDE)
- **Z_{α/2}** = 1.96 (two-tailed, 95% confidence)
- **Z_β** = 0.84 (80% power)

### Calculation Steps

1. **Pooled effect size calculation**:
   - p₁(1-p₁) = 0.41 × 0.59 = 0.2419
   - p₂(1-p₂) = 0.46 × 0.54 = 0.2484
   - Sum = 0.4903

2. **Effect denominator**:
   - (p₁ - p₂)² = (0.41 - 0.46)² = (-0.05)² = 0.0025

3. **Sample size per arm**:
   - n = 2 × (1.96 + 0.84)² × 0.4903 / 0.0025
   - n = 2 × (2.80)² × 0.4903 / 0.0025
   - n = 2 × 7.84 × 0.4903 / 0.0025
   - n = 7.6919 / 0.0025
   - **n ≈ 3,077 users per arm**

### Sample Size Summary

| Metric | Value |
|--------|-------|
| **Sample Size per Arm** | 3,077 users |
| **Total Sample Size** | 6,154 users |
| **Control Group** | 3,077 |
| **Treatment Group** | 3,077 |

## Feasibility Assessment

### Timeline to Recruit Sample

**Scenario 1: Using Only New Sign-ups**
- Eligible users per month: 3,750
- Total users needed: 6,154
- **Time required: 1.6 months** (~6 weeks)
- ✅ **Feasible** - Can recruit full sample in under 2 months

**Scenario 2: Using All Users (Including Existing)**
- If you include existing users who would re-engage with onboarding improvements: much faster
- **Time required: <1 month** (potentially 2-3 weeks)
- ✅ **Very Feasible**

## Statistical Power Assumptions

The calculated sample size assumes:
- ✅ Random assignment to control/treatment
- ✅ Independent observations
- ✅ True effect size = 5 percentage points
- ✅ No attrition or dropout bias
- ✅ Consistent response rates between groups

## Sensitivity Analysis

### Impact of Deviations from Baseline

| Scenario | Baseline | MDE | Sample Size per Arm |
|----------|----------|-----|-------------------|
| **Conservative** | 40% | +5pp | 3,045 |
| **Base Case** | 41% | +5pp | 3,077 |
| **Optimistic** | 42% | +5pp | 3,108 |

*Note: Small variations in baseline have minimal impact on required sample size*

### Varying MDE

| MDE | Required n per arm | Time to Recruit (months) |
|-----|------------------|----------------------|
| +3pp | 8,546 | 2.3 |
| +4pp | 4,814 | 1.3 |
| +5pp | 3,077 | 0.8 |
| +6pp | 2,136 | 0.6 |
| +7pp | 1,574 | 0.4 |

*Smaller detectable effects require proportionally larger samples*

## Practical Recommendations

### 1. **Sample Size Decision**
- **Minimum**: 3,077 per arm (6,154 total) for baseline specifications
- Consider padding to **3,200 per arm** (~6,400 total) to account for:
  - Potential dropouts or incomplete sessions
  - Data quality filtering
  - Early stopping or reallocation

### 2. **Recruitment Window**
- At 3,750 new sign-ups/month, you'll reach 6,400 total in **~1.7 months** (7 weeks)
- Recommended test duration: **6-8 weeks** for comfortable margin

### 3. **Traffic Allocation**
- Run as 50/50 split between control and treatment
- Ensures balanced statistical properties
- Minimizes variance in estimates

### 4. **Monitoring During Test**
- Check for balance between groups on day 1
- Monitor completion rates daily for obvious issues
- Plan for interim analysis only if using sequential testing plan
- Otherwise, run test to completion before analyzing

### 5. **Success Metrics Beyond Primary**
Consider tracking secondary metrics:
- Step-by-step completion rates (identify drop-off points)
- Time to complete onboarding
- Post-onboarding activation rate
- 30-day retention/engagement

## Expected Outcome Interpretation

With n=3,077 per arm:
- If true effect = +5pp: You'll detect it with 80% probability
- If true effect < 5pp: Higher probability of not detecting (Type II error)
- If true effect > 5pp: Will definitely detect with >80% probability
- Confidence intervals will be ±~3.5pp around observed effect

## Implementation Notes

1. **Stratification**: Consider blocking by company size, industry, or country if major onboarding differences exist
2. **Temporal Effects**: Watch for day-of-week or seasonal patterns in onboarding behavior
3. **Multiple Testing**: If testing multiple wizard variants, adjust sample size using Bonferroni correction
4. **Minimum Viable Sample**: If resource-constrained, could reduce to 2,500 per arm (80% power becomes ~70%), but not recommended

---

## Summary

**You need 3,077 users per group (6,154 total)** to detect a 5 percentage point improvement in onboarding completion from 41% to 46% with 95% confidence and 80% power. With 3,750 new sign-ups monthly, this is easily achievable in **under 2 months** and represents **less than 0.5% of your total user base**, making this test very practical to implement.
