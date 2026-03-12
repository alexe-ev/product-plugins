# Sample Size Estimation: Trial-to-Paid Email Test

## Status
**Incomplete setup for sample size estimation**

Cannot proceed with a defensible sample size or duration estimate without the following mandatory inputs.

---

## What We Know
- **Primary metric:** Trial-to-paid conversion rate
- **Baseline conversion rate:** 12.3%
- **Eligible traffic:** 4,500 trial expiry emails per week
- **Test type:** A/B test on email design

---

## Missing Mandatory Inputs

### 1. Minimum Detectable Effect (MDE)
**Why it matters:** This defines the smallest uplift worth detecting. Sample size grows dramatically as the target effect shrinks.

**What to decide:**
- What is the minimum uplift (in percentage points or relative %) that would justify launching the new email design?
- Example options:
  - Absolute uplift: +0.5 percentage points (12.3% → 12.8%)
  - Absolute uplift: +1.0 percentage point (12.3% → 13.3%)
  - Relative uplift: +5% (12.3% → 12.93%)
  - Relative uplift: +10% (12.3% → 13.53%)

### 2. Confidence Level (Significance)
**Why it matters:** This controls the false-positive rate. Higher confidence = larger sample requirement.

**Standard defaults:**
- 95% confidence level (α = 0.05) — most common in product experimentation
- 90% confidence level (α = 0.10) — faster but higher false-positive risk
- 99% confidence level (α = 0.01) — slower but lower false-positive risk

**Recommendation:** Use 95% if unsure; this is industry standard.

### 3. Statistical Power
**Why it matters:** This controls the false-negative rate (risk of missing a real effect). Higher power = larger sample requirement.

**Standard defaults:**
- 80% power (β = 0.20) — most common; accepts 20% risk of missing a real effect
- 85% power (β = 0.15) — slightly more conservative
- 90% power (β = 0.10) — very conservative; requires larger sample

**Recommendation:** Use 80% if unsure; this is industry standard.

---

## What Can Be Said Now

✓ **Baseline is strong:** 12.3% is a solid baseline with good historical data.

✓ **Traffic is sufficient:** 4,500 emails per week is reasonable for most experiment designs.

✗ **Duration cannot be estimated** until we know the required sample size, which depends entirely on MDE, confidence, and power.

---

## How to Move Forward: Setup Checklist

Before rerunning the estimation, please provide:

1. **Minimum Detectable Effect**
   - [ ] Decided on absolute or relative uplift
   - [ ] Specified the exact magnitude
   - [ ] Confirmed alignment with product goals

2. **Confidence Level**
   - [ ] Chosen from standard options (90%, 95%, or 99%)
   - [ ] Or confirmed acceptance of 95% default

3. **Statistical Power**
   - [ ] Chosen from standard options (80%, 85%, or 90%)
   - [ ] Or confirmed acceptance of 80% default

---

## Scenario-Based Guidance (For Planning)

To help with internal discussions, here are example scenarios showing how different MDE assumptions affect sample size and duration. These are **not estimates** but illustrative scenarios only.

### Scenario A: Detect a 1 percentage point uplift (12.3% → 13.3%)
Using standard assumptions (95% confidence, 80% power):
- Estimated sample size per group: ~5,900 users
- Total required sample: ~11,800 users
- Estimated duration: ~2.6 weeks

### Scenario B: Detect a 0.5 percentage point uplift (12.3% → 12.8%)
Using standard assumptions (95% confidence, 80% power):
- Estimated sample size per group: ~23,500 users
- Total required sample: ~47,000 users
- Estimated duration: ~10.4 weeks

### Scenario C: Detect a 10% relative uplift (12.3% → 13.53%)
Using standard assumptions (95% confidence, 80% power):
- Estimated sample size per group: ~4,500 users
- Total required sample: ~9,000 users
- Estimated duration: ~2 weeks

---

## Inputs Used
- Metric type: Conversion (trial-to-paid)
- Baseline: 12.3%
- Eligible traffic: 4,500 trial expiry emails per week
- Split ratio: Assumed 50/50 (even split)

---

## Inputs NOT Provided
- Minimum detectable effect ❌
- Confidence level ❌
- Statistical power ❌

---

## Assumptions
- Two-variant fixed-horizon A/B test
- Even traffic split (50% control, 50% treatment)
- 4,500 weekly traffic is stable and represents all eligible trial expiry emails
- No major shifts in email deliverability, list quality, or trial cohort characteristics

---

## Feasibility Note
Once MDE, confidence, and power are decided:
- If the required duration is 2–4 weeks: highly feasible
- If the required duration is 4–8 weeks: feasible but consider business cadence
- If the required duration is >8 weeks: reassess MDE (may need larger effect or accept higher risk)

---

## Next Steps
1. Align with product/analytics leadership on the minimum meaningful uplift
2. Confirm confidence and power assumptions (or accept defaults)
3. Rerun this estimation with complete inputs
4. Review feasibility of the resulting duration against your launch timeline
