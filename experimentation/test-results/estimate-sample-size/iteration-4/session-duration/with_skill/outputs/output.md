# Sample Size Estimation: In-App Coaching Feature (Session Duration)

## Input Summary

**Primary metric:** Average session duration (continuous)

**Baseline:** 6.5 minutes

**Standard deviation:** 12 minutes (from historical data)

**Minimum detectable effect (δ):** +0.8 minutes

**Confidence level:** 95%

**Statistical power:** 80%

**Eligible traffic:** 15,000 users per week

**Split ratio:** 50/50 (control and treatment)

---

## Calculation

Using the explicit continuous metric formula from REFERENCE.md:

```
n_per_group = (z_α/2 + z_β)² × 2σ² / δ²
```

**Step 1: Z-score calculation**
- For 95% confidence (two-sided): z_α/2 = 1.96
- For 80% power: z_β = 0.84
- (z_α/2 + z_β)² = (1.96 + 0.84)² = (2.80)² = **7.84**

**Step 2: Variance term**
- 2σ² = 2 × (12)² = 2 × 144 = **288**

**Step 3: Effect size squared**
- δ² = (0.8)² = **0.64**

**Step 4: Sample size per group**
- n_per_group = 7.84 × 288 / 0.64
- n_per_group = 2,257.92 / 0.64
- **n_per_group = 3,528 users**

**Step 5: Total sample size**
- Total = 3,528 × 2 = **7,056 users**

**Step 6: Estimated test duration**
- Duration = Total sample / Eligible traffic per week
- Duration = 7,056 / 15,000 = **0.47 weeks**
- **≈ 3.3 days**

---

## Results

| Metric | Value |
|--------|-------|
| Sample size per group | 3,528 users |
| Total sample size | 7,056 users |
| Estimated duration | 3.3 days |
| Confidence level | 95% |
| Statistical power | 80% |

---

## Inputs Used

- Continuous metric (average session duration)
- Baseline: 6.5 minutes
- Standard deviation: 12 minutes
- Minimum detectable effect: +0.8 minutes
- Significance level: 0.05 (95% confidence)
- Power: 0.80
- Eligible traffic: 15,000 users per week
- Even 50/50 split

---

## Assumptions

- Two-variant fixed-horizon A/B test (control vs. treatment)
- Standard deviation of 12 minutes is accurate and stable across both variants
- Eligible traffic of 15,000 users per week is consistent and unaffected by seasonality or major traffic shifts
- Session duration is approximately normally distributed
- Each user is exposed to only one variant and counted once
- No interference or spillover effects between variants

---

## Feasibility Assessment

**Status: HIGHLY FEASIBLE**

- Required sample size (7,056) is small relative to eligible traffic (15,000/week)
- Test duration (~3.3 days) is very short and practical
- Easy to execute within typical business cadences
- No risk of traffic saturation or resource constraints
- Sufficient time to account for minor traffic fluctuations

---

## Notes and Caveats

1. **Duration estimate is directional:** The 3.3-day estimate assumes constant, uniform eligible traffic. Real-world variations (weekday/weekend patterns, holidays, campaign overlaps) may extend actual duration.

2. **Standard deviation stability:** The estimate relies on the historical standard deviation of 12 minutes being representative of future conditions. If the treatment significantly changes variance, power may shift.

3. **Sample independence:** The calculation assumes each eligible user is counted once. If users can be re-exposed or appear in multiple periods, adjust the eligible traffic estimate accordingly.

4. **Practical considerations:** Even though statistical power is 80%, real-world results may differ due to:
   - User experience variability
   - External factors (campaigns, product changes, seasonality)
   - Session definition consistency

5. **Effect interpretation:** An +0.8-minute increase in average session length (~12% relative lift from 6.5-minute baseline) is a meaningful threshold. Verify this aligns with product and business goals.

---

## Next Steps

1. **Approve the test plan** with these sample size and duration estimates
2. **Implement randomization** ensuring 50/50 split
3. **Activate monitoring** for session duration metrics in control and treatment
4. **Run for ~3.3 days** (or slightly longer to account for traffic variance)
5. **Analyze results** using intent-to-treat (ITT) analysis
6. **Document learnings** on whether the +0.8-minute MDE was achieved, and at what confidence

---

## Skill Metadata

- **Skill:** estimate-sample-size
- **Metric Type:** Continuous
- **Formula Used:** n_per_group = (z_α/2 + z_β)² × 2σ² / δ²
- **Confidence:** 95% (α = 0.05, two-sided)
- **Power:** 80% (β = 0.20)
- **Date Generated:** 2026-03-11
