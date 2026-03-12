# A/B Test Sample Size Calculation: In-App Coaching Feature

## Objective
Test whether a new in-app coaching feature increases session length.

---

## Test Parameters

| Parameter | Value |
|-----------|-------|
| **Baseline mean session duration** | 6.5 minutes |
| **Standard deviation** | 12 minutes |
| **Minimum detectable effect (MDE)** | +0.8 minutes (+12.3% relative) |
| **Confidence level** | 95% (two-tailed) |
| **Statistical power** | 80% |
| **Eligible traffic** | 15,000 users/week |
| **Test split** | 50/50 (Control vs Treatment) |

---

## Step-by-Step Calculation

### Step 1: Determine Z-Scores

For a two-sample t-test with continuous outcomes:

- **Z-score for 95% confidence level (α = 0.05, two-tailed):** z_α = 1.96
- **Z-score for 80% power (β = 0.20, one-tailed):** z_β = 0.84

### Step 2: Pooled Standard Deviation

Assuming equal variances between control and treatment groups:

- **Pooled SD = 12 minutes**

### Step 3: Apply Sample Size Formula

For continuous outcomes with equal sample sizes:

```
n = 2 × (z_α + z_β)² × SD² / MDE²
```

**Substituting values:**

```
n = 2 × (1.96 + 0.84)² × 12² / 0.8²
n = 2 × (2.8)² × 144 / 0.64
n = 2 × 7.84 × 144 / 0.64
n = 2,257.92 / 0.64
n = 3,528
```

### Step 4: Sample Size Results

- **Sample size per group:** 3,528 users
- **Total sample size required:** 7,056 users

### Step 5: Timeline to Reach Sample Size

```
Days needed = (Total sample size / Eligible traffic per week) × 7
Days needed = (7,056 / 15,000) × 7
Days needed = 0.47 weeks ≈ 3.3 days
```

### Step 6: Effect Size Analysis

**Cohen's d (standardized effect size):**

```
Cohen's d = MDE / SD = 0.8 / 12 = 0.0667
```

- Small effect: d ≈ 0.2
- Medium effect: d ≈ 0.5
- Large effect: d ≈ 0.8

This is a **very small effect size** (0.0667), which explains why the relatively large sample size (3,528 per group) is needed to detect such a subtle improvement with high confidence and power.

---

## Statistical Power Summary

| Metric | Value |
|--------|-------|
| **Type I error (α)** | 5% (significance level) |
| **Type II error (β)** | 20% |
| **Power (1 - β)** | 80% |
| **Minimum detectable effect** | +0.8 minutes (12.3% relative increase) |

---

## Recommendation

**✓ SAMPLE SIZE IS ACHIEVABLE**

- **Required sample size:** 3,528 users per group
- **Total required:** 7,056 users
- **Time to completion:** ~3.3 days (0.47 weeks)
- **Available traffic:** 15,000 users/week

Your eligible traffic of 15,000 users per week is more than sufficient to reach the required sample size in under 4 days, allowing for a quick, statistically rigorous test of the in-app coaching feature.

---

## Assumptions

1. Session duration follows a normal distribution (or approximately normal with large sample size)
2. Equal variances in both control and treatment groups
3. Independent observations with no overlap between test groups
4. Consistent traffic patterns (no major changes during test period)
5. No learning effects or carryover effects between groups

---

## Next Steps

1. Randomize 7,056 users into control (3,528) and treatment (3,528) groups
2. Run test for ~3-4 days until sample size is reached
3. Conduct statistical analysis using two-sample t-test
4. Analyze session duration metrics: mean, median, 95th percentile
5. Consider secondary metrics: user engagement, feature adoption rate
