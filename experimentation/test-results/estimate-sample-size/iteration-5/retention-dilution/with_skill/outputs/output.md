# Sample Size Estimate: 30-Day Retention Experiment

## Inputs Summary
- **Primary metric:** 30-day retention rate
- **Baseline retention:** 42%
- **Target retention:** 45% (baseline + 3 percentage points)
- **Confidence level:** 95% (two-sided)
- **Statistical power:** 80%
- **New user acquisition:** 5,000 users per week
- **Split ratio:** 50/50 (control vs. treatment)
- **Cohort dilution:** 15% (unmeasurable users before the 30-day window closes)

## Calculation

### Step 1: Calculate effective sample size using binomial formula

For a conversion/rate metric:
```
n_effective_per_group = (z_α/2 + z_β)² × (r1×(1−r1) + r2×(1−r2)) / (r2 − r1)²
```

Where:
- z_α/2 = 1.96 (95% confidence, two-sided)
- z_β = 0.84 (80% power)
- r1 = 0.42 (baseline 42%)
- r2 = 0.45 (target 45%)
- (r2 − r1) = 0.03 (3 percentage points)

Calculation:
- (1.96 + 0.84)² = 2.8² = 7.84
- r1×(1−r1) = 0.42 × 0.58 = 0.2436
- r2×(1−r2) = 0.45 × 0.55 = 0.2475
- Sum of variances: 0.2436 + 0.2475 = 0.4911
- (r2 − r1)² = 0.03² = 0.0009

**n_effective_per_group = 7.84 × 0.4911 / 0.0009 = 4,278 users per group**

### Step 2: Apply dilution adjustment

Since 15% of enrolled users become unmeasurable, we must adjust the enrolled sample upward:

```
n_enrolled_per_group = n_effective_per_group / (1 − dilution_rate)
n_enrolled_per_group = 4,278 / (1 − 0.15) = 4,278 / 0.85 = 5,033 users per group
```

## Results

- **Enrolled sample per group:** 5,033 users
- **Total enrolled sample:** 10,066 users (5,033 × 2)

## Estimated Duration

```
duration = total_enrolled_sample / eligible_new_users_per_week
duration = 10,066 / 5,000 = 2.01 weeks
```

**Estimated test duration:** ~2.0 weeks

## Important Clarifications

### Eligible Traffic Definition
For retention experiments, "eligible traffic" refers to **new users entering the cohort per period**, not total active users or overall app traffic. This is critical because the retention metric is measured against cohort members, not against your entire user base. In this case, you have 5,000 new user enrollments per week, which is the correct traffic metric for duration estimation.

## Assumptions & Caveats

1. **Cohort dilution adjustment:** The 15% dilution rate accounts for users lost to app uninstalls, attribution issues, or other causes before the 30-day measurement window closes. This adjustment increases the enrolled sample size from 4,278 to 5,033 per group to ensure you still have enough measurable users to detect the effect.

2. **Constant new user acquisition:** The duration estimate assumes a steady flow of 5,000 new users per week with no major spikes or drops.

3. **Measurement window:** The 30-day retention window is assumed to be cleanly measurable for all enrolled users (subject to the 15% dilution already accounted for).

4. **Traffic patterns:** Weekly cycles, seasonality, or campaign-driven acquisition spikes are not accounted for. If your user acquisition varies significantly by day or week, adjust the timeline accordingly.

## Feasibility Note

This experiment is **highly feasible**. With 5,000 new users per week, you'll have sufficient traffic to reach the required enrolled sample (10,066 total) in approximately 2 weeks. The sample sizes per group (5,033) are achievable and reasonable for a retention test of this scale.
