# A/B Test Sample Size Calculation: Email Subject Line Format

## Test Parameters
- **Primary Metric**: Email open rate (conversion rate)
- **Baseline Conversion Rate**: 22%
- **Minimum Detectable Effect (MDE)**: +2 percentage points
- **Confidence Level**: 95% (α = 0.05)
- **Statistical Power**: 80% (β = 0.20)
- **Total Eligible Traffic**: 8,000 emails per week
- **Traffic Split**: 50/50 (Control vs. Treatment)

## Step-by-Step Calculation

### Step 1: Convert percentages to proportions
- **p₁** (Baseline/Control): 0.22
- **p₂** (Expected Treatment): 0.22 + 0.02 = 0.24
- **Δp** (Absolute difference): 0.02

### Step 2: Calculate pooled proportion
For two-proportion z-test:
- **p̄** = (p₁ + p₂) / 2
- **p̄** = (0.22 + 0.24) / 2 = 0.23

### Step 3: Identify critical z-values
- **Two-tailed test at 95% confidence (α = 0.05)**: z_{α/2} = 1.96
- **Power = 80% (β = 0.20)**: z_β = 0.84

### Step 4: Apply sample size formula
For comparing two independent proportions:

**n = [(z_{α/2} + z_β)² × (p₁(1-p₁) + p₂(1-p₂))] / (p₂ - p₁)²**

Breaking down the numerator:
- p₁(1-p₁) = 0.22 × 0.78 = 0.1716
- p₂(1-p₂) = 0.24 × 0.76 = 0.1824
- Sum = 0.3540

Calculating:
- (z_{α/2} + z_β)² = (1.96 + 0.84)² = (2.80)² = 7.84
- Numerator: 7.84 × 0.3540 = 2.7754
- Denominator: (0.02)² = 0.0004

**n = 2.7754 / 0.0004 = 6,938.5**

### Step 5: Round up and apply to both groups
- **Sample size per group**: 6,939 participants
- **Total sample size needed**: 2 × 6,939 = **13,878 participants**

## Feasibility Assessment

### Weekly Traffic Capacity
- Total eligible traffic: 8,000 emails/week
- Total sample needed: 13,878 emails
- **Weeks required**: 13,878 / 8,000 = **1.73 weeks** (approximately 12 days)

### 50/50 Split Allocation
- **Control group**: 6,939 emails
- **Treatment group**: 6,939 emails
- **Weekly allocation (50/50)**:
  - Control: 4,000 emails/week
  - Treatment: 4,000 emails/week

## Statistical Power Analysis

At n = 6,939 per group with given parameters:
- Able to detect a 2 percentage point difference (22% → 24%) with 80% probability
- 5% significance level (two-tailed) protects against false positives
- Expected effect size: Cohen's h = 2 × arcsin(√0.24) - 2 × arcsin(√0.22) ≈ 0.0432 (small effect)

## Key Insights

1. **Sample requirement is feasible**: 13,878 total participants can be collected in under 2 weeks with current traffic levels
2. **Statistical precision**: With this sample size, we can confidently detect a 2pp improvement if it truly exists
3. **Multiple-week test likely needed**: To ensure sufficient time for email delivery, open tracking, and to account for weekly email patterns, allocate 2-3 weeks for data collection
4. **Recommendation**: Run test for 2 full weeks to safely accumulate all required samples while accounting for delivery and tracking latency

## Assumptions
- Open rate tracking is accurate and complete
- No significant day-of-week or week-of-month effects
- Random assignment to control/treatment groups
- Independent observations (no user appears in multiple groups)
- Eligible traffic remains stable at 8,000 emails/week
