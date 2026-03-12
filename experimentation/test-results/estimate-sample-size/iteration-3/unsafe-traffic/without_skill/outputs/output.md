# Sample Size Estimation: B2B Onboarding Wizard Test

## Problem Statement
Testing a new onboarding wizard in a B2B project management tool with 25,000 registered users. Need to determine sample size for detecting a 5 percentage point improvement in onboarding completion rate.

## Inputs
- **Primary Metric:** Onboarding completion rate
- **Baseline (p₀):** 41% = 0.41
- **Minimum Detectable Effect (MDE):** +5 percentage points
- **Target Rate (p₁):** 46% = 0.46
- **Confidence Level:** 95% (α = 0.05)
- **Power:** 80% (β = 0.20)
- **Population:** 25,000 registered users; 15% new sign-ups monthly = 3,750 eligible users

## Calculation Steps

### Step 1: Z-Score Determination
For a two-tailed test:
- Z_α/2 (95% confidence) = **1.96**
- Z_β (80% power) = **0.84**

### Step 2: Pooled Proportion
```
p̄ = (p₀ + p₁) / 2
p̄ = (0.41 + 0.46) / 2
p̄ = 0.435
```

### Step 3: Sample Size Formula Application
Using the two-proportion comparison formula:
```
n = (Z_α/2 + Z_β)² × [p₀(1-p₀) + p₁(1-p₁)] / (p₁ - p₀)²
```

**Numerator Components:**
- (Z_α/2 + Z_β)² = (1.96 + 0.84)² = (2.80)² = **7.84**
- p₀(1-p₀) = 0.41 × 0.59 = **0.2419**
- p₁(1-p₁) = 0.46 × 0.54 = **0.2484**
- Sum of proportions: **0.4903**

**Denominator:**
- (p₁ - p₀)² = (0.46 - 0.41)² = (0.05)² = **0.0025**

**Calculation:**
```
n = (7.84 × 0.4903) / 0.0025
n = 3.8415 / 0.0025
n = 1,536.6
```

### Step 4: Sample Size per Group
```
Per-group sample size = 1,537 users (rounded up)
```

### Step 5: Total Sample Size (Two-Group Test)
```
Total sample size = 1,537 × 2 = 3,074 users
```

## Results

| Metric | Value |
|--------|-------|
| **Sample size per group** | 1,537 users |
| **Total sample size** | 3,074 users |
| **Control group** | 1,537 users |
| **Treatment group** | 1,537 users |

## Feasibility Assessment

**Population Availability:**
- Monthly new sign-ups (eligible for onboarding): 3,750 users
- Required sample size: 3,074 users
- **Coverage:** 82% of monthly eligible users (feasible within 1 month)

**Timeline Recommendation:**
- Collect sample within ~1 month of new registrations
- This provides sufficient sample while maintaining fresh user cohort homogeneity

## Statistical Interpretation
With 3,074 total participants (1,537 per group), this test has:
- 95% confidence that any observed difference is not due to random chance
- 80% power to detect a true 5 percentage point improvement in completion rate
- Ability to distinguish between 41% baseline and 46% target rate
- If the true effect is ≥5pp improvement, there's an 80% chance the test will detect it

## Key Assumptions
1. Users are randomly assigned to control or treatment groups
2. Completion rates are independent across users
3. No significant confounding variables affect completion
4. Baseline rate remains stable at 41% during test period
5. New sign-up cohort is representative of typical onboarding population
