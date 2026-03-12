# Sample Size Estimation: B2B Onboarding Wizard Test

## Summary

**Sample size per group:** ~3,078 users
**Total sample size:** ~6,156 users
**Estimated duration:** Cannot be reliably estimated (see warning below)

---

## Inputs Used

| Parameter | Value |
|-----------|-------|
| **Metric type** | Conversion rate (onboarding completion) |
| **Baseline rate** | 41% |
| **Target rate** | 46% |
| **Absolute effect size** | +5 percentage points |
| **Confidence level** | 95% (α = 0.05, two-tailed) |
| **Statistical power** | 80% (β = 0.20) |
| **Split ratio** | 50/50 (assumed) |
| **Total platform users** | 25,000 |
| **Eligible segment** | 15% (new sign-ups per month) |
| **Estimated eligible traffic** | ~3,750 per month (~868 per week) |

---

## Calculation Details

**Formula:** Two-proportion test sample size
n = 2 × (z_α/2 + z_β)² × [p₁(1-p₁) + p₂(1-p₂)] / (p₂ - p₁)²

**Parameters:**
- z_α/2 = 1.96 (95% confidence, two-tailed)
- z_β = 0.84 (80% power)
- p₁ = 0.41 (baseline)
- p₂ = 0.46 (implied target)
- Δp = 0.05 (effect size)

**Numerator:** 2 × 7.84 × 0.4903 = 7.683
**Denominator:** 0.0025
**Per-group sample size:** ~3,078 users
**Total sample size:** ~6,156 users

---

## Assumptions

1. **Two-variant fixed-horizon A/B test** with equal allocation to control and treatment.
2. **Metric is binary** (completion vs. non-completion).
3. **Independent observations** within each group.
4. **No sequential or adaptive stopping** during the test.
5. **Traffic stability** across the test period (no major seasonal shifts, campaign changes, or traffic quality shifts).
6. **Minimum detectable effect of +5 percentage points is meaningful** to your business.
7. **50/50 traffic split** between control and treatment.

---

## Feasibility Assessment

### ⚠️ Critical Traffic Warning

**Problem:** The input mixes total product traffic with eligible traffic.

You provided:
- Total platform users: 25,000
- Eligible segment: 15% (new sign-ups per month)

**This is unsafe because:**
- The test should only include users who go through onboarding (new sign-ups).
- Not all 25,000 users are eligible; only the ~3,750 monthly new sign-ups (15%) qualify.
- Using total traffic for duration estimation would dramatically underestimate the actual test length.

### Duration Estimate Status: **BLOCKED**

The skill cannot reliably estimate calendar duration without confirming:
1. **Weekly or monthly flow of new sign-ups** into onboarding (clarify whether 15% = 3,750 per month, and how this distributes weekly).
2. **Whether 15% is stable** across the test period or varies seasonally.
3. **Whether all new sign-ups are actually eligible** for the test (e.g., are some excluded by region, plan type, or other criteria?).

### Current Feasibility Range (Directional)

If we assume **~868 new sign-ups per week** (3,750 / 4.3 weeks):

**Estimated duration: ~7 weeks** (6,156 required / 868 per week)

**This is a rough estimate only.** Actual duration depends on:
- Exact weekly eligible traffic
- Whether traffic is stable
- Any exclusion criteria not yet mentioned

### Feasibility Concerns

1. **Test duration may be acceptable but non-trivial** for a B2B product. Seven weeks is reasonable for an important onboarding change.
2. **Sample size is moderate** relative to your eligible traffic pool, which is positive.
3. **The 5 percentage point effect is meaningful** for an onboarding metric and worth testing.

---

## Recommendations

### Before launching the test:

1. **Confirm weekly eligible traffic:**
   - How many new sign-ups enter onboarding each week?
   - Is this stable, or does it vary by season/marketing cadence?

2. **Clarify any exclusions:**
   - Are there user segments ineligible for the test (e.g., free trial users, specific regions, users from integrations)?
   - If so, reduce the eligible traffic estimate accordingly.

3. **Decide on test duration tolerance:**
   - If 7 weeks is too long, consider whether a 3–4 percentage point effect might also be valuable (smaller MDE = faster test).
   - If 7 weeks is acceptable, proceed with the 5 percentage point effect.

4. **Plan for traffic variability:**
   - Monitor weekly eligible traffic during the test.
   - If weekly signup volume is lower than expected, extend the test runway.

---

## Missing Inputs (Not Fatal, But Useful)

- **Exact weekly eligible traffic** (provided as a range: "15% per month")
- **Seasonality or acquisition patterns** in new sign-ups
- **Segment exclusions** (e.g., are enterprise users excluded? free-tier only?)
- **Expected completion rate variance** (the baseline 41% is clear; no variance assumption needed for this calculation)

---

## Output Interpretation

| Metric | Value | Meaning |
|--------|-------|---------|
| Per-group sample | ~3,078 | Each variant needs roughly 3,000 new users going through onboarding. |
| Total sample | ~6,156 | Combined across control and treatment. |
| Duration | ~7 weeks | Rough estimate if eligible traffic is ~868/week and stable. |

---

## Trust Caveats

- **Duration estimate is directional, not guaranteed.** Real-world traffic varies week-to-week.
- **The calculation assumes the baseline 41% is stable.** If new user cohorts differ in onboarding behavior, adjust expectations.
- **The MDE of +5 percentage points was your input; verify this is achievable with your treatment variant.**
- **Do not use total platform users (25,000) for traffic modeling.** Focus on new sign-ups entering onboarding each week.

---

## Next Steps

1. **Validate eligible traffic:** Confirm new sign-up volume per week.
2. **Review feasibility:** Confirm 7-week test window is acceptable.
3. **Finalize hypothesis:** Ensure +5 percentage point lift is the target effect.
4. **Prepare randomization:** Plan how to randomly assign new onboarding users to control vs. treatment.
5. **Hand off to design-experiment-plan skill** (if available) for implementation details.

