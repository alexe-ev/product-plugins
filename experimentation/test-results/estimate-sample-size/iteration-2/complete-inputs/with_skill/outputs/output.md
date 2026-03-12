## Sample Size Estimation: Food Delivery App Click-to-Order Test

### Input Summary
**Primary metric:** Click-to-order conversion rate
**Baseline:** 7.8%
**Minimum detectable effect:** +0.8 percentage points (absolute)
**Confidence level:** 95%
**Statistical power:** 80%
**Eligible traffic:** 35,000 users per week
**Split ratio:** 50/50

---

### Results

**Sample size per group:**
~18,542 users

**Total sample size:**
~37,084 users

**Estimated duration:**
Approximately 1.1 weeks of eligible traffic

---

### Inputs Used
- Conversion metric (two-variant test)
- Baseline: 7.8%
- Target: 8.6% (implied by +0.8pp MDE)
- Confidence: 95% (α = 0.05, two-tailed)
- Power: 80% (β = 0.20)
- Even split (50/50)
- Eligible traffic: 35,000 users per week

---

### Assumptions
- Two-variant fixed-horizon A/B test
- Stable traffic quality and composition across the test period
- No major distortion from promotions, app launches, or acquisition source shifts during the test window
- Eligible traffic refers to users who actually reach and interact with the restaurant card and have an opportunity to click-to-order
- Traffic is evenly distributed across both variants
- No interaction or confounding effects from concurrent product experiments
- Conversion opportunity is independent across users

---

### Calculation Methodology
Used the standard two-proportion z-test sample size formula:

```
n = (Z_α/2 + Z_β)² × (p₁(1-p₁) + p₂(1-p₂)) / (p₂ - p₁)²
```

Where:
- Z_α/2 = 1.96 (95% confidence, two-tailed)
- Z_β = 0.84 (80% power)
- p₁ = 0.078 (baseline conversion)
- p₂ = 0.086 (target conversion)
- Effect size = 0.008 (0.8 percentage points)

Per-group sample size ≈ 18,542
Total sample size = 18,542 × 2 ≈ 37,084

---

### Feasibility Assessment

**Duration:** Very favorable. The test requires only ~1.1 weeks of traffic to reach the target sample size, well within typical business planning windows.

**Sample size:** Moderate. The required per-group sample (~18.5k) is achievable with 35,000 weekly eligible users.

**Traffic efficiency:** At 50/50 split, the test will consume ~51% of weekly eligible traffic (37,084 / 35,000 × 100 / 2 splits ≈ ~53% of weekly users per variant across the test period).

**Recommendation:** This test is **feasible**. The short duration (1–2 weeks depending on daily traffic variance) allows for:
- Quick iteration cycles
- Minimal business impact from the 50/50 split
- Clear signal if the effect size exists
- Early decision point to scale or iterate

---

### Caveats and Trust Notes

1. **Traffic consistency:** This estimate assumes 35,000 eligible users per week is consistent and stable. Weekly fluctuations or day-of-week effects may extend the actual duration by 20–30%.

2. **Minimum detectable effect:** A +0.8pp uplift (7.8% → 8.6%) represents a 10.3% relative improvement. This is a meaningful effect size. If the true effect is smaller, power will be reduced.

3. **Click-to-order eligibility:** The "eligible traffic" count should exclude:
   - Users not shown the restaurant card
   - Users in geographies without restaurant coverage
   - Users blocked by other feature flags

   If actual eligible traffic is lower, duration will increase proportionally.

4. **External factors:** The estimate may not account for:
   - App version rollout pacing
   - Seasonal demand shifts during the test window
   - Competing product launches or features
   - Traffic source or user cohort changes

5. **Assumed equal variance:** The calculation assumes baseline and variant conversion rates have similar variance. For very low-rate metrics (<1%), consider consulting with a statistician.

---

### Downstream Handoff

This estimate is ready for:
- **Experiment design documentation** (design-experiment-plan skill)
- **Launch timeline planning:** Test can begin within 1–2 weeks and conclude in ~1 week
- **Feasibility reviews:** Traffic is sufficient; duration is short; no major blocking constraints detected
- **Stakeholder communication:** "We need ~37k users to detect an 0.8pp lift with 95% confidence and 80% power. At our current traffic, this takes about 1 week."

---

### Next Steps

1. Validate that 35,000 users per week actually reach the restaurant card test point
2. Define control vs. variant experience in detail
3. Plan telemetry and instrumentation (ensure click-to-order event is cleanly tracked)
4. Check for interaction with concurrent experiments
5. Schedule test window (aim for stable traffic period with no major app updates)
