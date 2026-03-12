# Sample Size Estimate for Onboarding Flow A/B Test

## Problem

You want to test whether a redesigned onboarding flow reduces time to first action.

## Given Inputs

- **Metric type:** Continuous (time in minutes)
- **Baseline:** 8 minutes
- **Minimum detectable effect (MDE):** 30 seconds (0.5 minutes) — target 7.5 minutes
- **Confidence level:** 95%
- **Power:** 80%
- **Eligible traffic:** 3,000 new users per week

## Calculation Status

⚠️ **Blocked on missing required input**

## Why I can't give you a single sample size number yet

For continuous metrics like time-to-first-action, the sample size formula is:

```
n_per_group = (z_α/2 + z_β)² × 2σ² / δ²
```

Where:
- `z_α/2` = 1.96 (95% confidence)
- `z_β` = 0.84 (80% power)
- `δ` = 0.5 minutes (your MDE)
- `σ` = **standard deviation — MISSING**

Without the standard deviation of your baseline metric, the calculation cannot proceed reliably.

## How to Obtain the Standard Deviation

You have several options:

1. **Historical data:** Check your analytics or logs for the last 1–3 months of baseline time-to-first-action data. Calculate the standard deviation directly.

2. **Pilot test:** Run a small experiment (500–1,000 baseline users) and measure both mean and SD.

3. **Related experiments:** If you've tested onboarding changes before, use the SD from that baseline cohort.

4. **Industry benchmarks:** For mobile or web onboarding flows, typical SD ranges from 1.5× to 3× the mean, but this is less reliable than your own data.

## Scenario Estimates (Illustrative Only)

If you can estimate SD, here's how to interpret the results:

| Assumed SD | n per group | Total sample | Duration (weeks) |
|-----------|------------|--------------|------------------|
| 1.5 min   | 295        | 590          | ~0.2 weeks       |
| 2.5 min   | 818        | 1,636        | ~0.5 weeks       |
| 4.0 min   | 2,083      | 4,166        | ~1.4 weeks       |

**Important:** These are **directional only** and depend entirely on the SD assumption. If your actual SD is different, the required sample size will change significantly.

## Inputs Used

- Baseline: 8 minutes
- MDE: 0.5 minutes absolute (6.25% relative)
- Confidence: 95% (α = 0.05, two-tailed)
- Power: 80% (β = 0.20)
- Eligible traffic: 3,000 new users/week
- Z-values: z_α/2 = 1.96, z_β = 0.84

## Missing Inputs

- **Standard deviation of baseline time-to-first-action (required)**

## Assumptions

- Normal distribution (reasonable for time-to-action if not heavily right-skewed)
- No cohort dilution
- Uniform traffic across the week
- Linear relationship between sample size and SD

## Feasibility Note

With 3,000 eligible new users per week, once you provide SD, you'll likely have a test that runs 1–3 weeks. This is practical if your SD is moderate (1.5–3 minutes). If SD is very high (>5 min), you may need 4+ weeks, which could slow your iteration cycle.
