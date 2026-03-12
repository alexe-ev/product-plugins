# Sample Size Estimation: SaaS Trial Expiry Email Test

## Status
**Incomplete setup for sample size estimation**

The inputs provided are helpful but not sufficient for a defensible sample size and duration calculation. Three mandatory inputs are missing.

---

## Inputs Provided

**Primary metric type:** Trial-to-paid conversion rate

**Baseline metric value:** 12.3%

**Eligible traffic:** 4,500 trial expiry emails per week

**Product context:** SaaS trial expiry email sequence, testing new email design

---

## Missing Mandatory Inputs

To estimate sample size and test duration, the following must be defined:

1. **Minimum Detectable Effect (MDE)**
   - What relative or absolute uplift would make the new design "worth it"?
   - Examples:
     - Absolute: +0.5 percentage points (from 12.3% → 12.8%)
     - Relative: +5% (from 12.3% → 12.9%)
     - Relative: +10% (from 12.3% → 13.5%)

2. **Confidence Level (Significance Level)**
   - What statistical confidence do you want?
   - Standard choice: 95% confidence (α = 0.05)
   - More conservative: 99% confidence (α = 0.01)

3. **Statistical Power**
   - How often should the test detect the effect if it truly exists?
   - Standard choice: 80% power (β = 0.20)
   - More conservative: 90% power (β = 0.10)

---

## What Can Be Said Now

- **Eligible traffic is known:** 4,500 trial expiry emails per week is a concrete, helpful constraint
- **Baseline is known:** 12.3% is a clear starting point
- **Duration estimation is blocked:** Without knowing the required sample size, duration cannot be calculated
- **Sample size estimation is blocked:** MDE choice determines the effect size; confidence and power determine the z-scores used in the calculation

---

## Scenario Ranges (Illustration Only)

To give you a sense of what different choices mean, here are illustrative scenarios. **These are NOT recommendations—your team must decide the MDE, confidence, and power based on business priorities.**

### Scenario A: Modest effect, standard statistical settings
- **Assumptions:** 5% relative uplift, 95% confidence, 80% power
- **Effect:** 12.3% → 12.9%
- **Estimated sample size per group:** ~2,600 users
- **Total sample size:** ~5,200 users
- **Estimated duration:** ~1.2 weeks (5,200 ÷ 4,500)
- **Feasibility:** Very practical

### Scenario B: Smaller effect, standard statistical settings
- **Assumptions:** 2% relative uplift, 95% confidence, 80% power
- **Effect:** 12.3% → 12.6%
- **Estimated sample size per group:** ~6,500 users
- **Total sample size:** ~13,000 users
- **Estimated duration:** ~2.9 weeks (13,000 ÷ 4,500)
- **Feasibility:** Practical

### Scenario C: Larger effect, standard statistical settings
- **Assumptions:** 10% relative uplift, 95% confidence, 80% power
- **Effect:** 12.3% → 13.5%
- **Estimated sample size per group:** ~1,050 users
- **Total sample size:** ~2,100 users
- **Estimated duration:** ~0.47 weeks (~3 days)
- **Feasibility:** Very easy

---

## Recommended Next Steps

1. **Define the MDE** with your product and analytics teams:
   - What uplift would justify the engineering investment in the new email design?
   - What is the smallest effect you'd regret missing?

2. **Confirm statistical settings** (or use defaults):
   - 95% confidence and 80% power are industry standard for product experiments
   - If higher risk tolerance, consider 90% confidence and 80% power (smaller sample)
   - If lower risk tolerance, consider 95% confidence and 90% power (larger sample)

3. **Once MDE, confidence, and power are set**, this skill can provide:
   - Precise sample size per group and total
   - Estimated test duration based on your 4,500 weekly emails
   - Feasibility assessment

---

## Notes on Eligible Traffic

Your 4,500 trial expiry emails per week are the correct base for duration estimation. This is the traffic that can actually enter the test, so the sample size will be divided by this to estimate how many weeks the test must run.

**Caution:** If not all 4,500 recipients complete the conversion funnel within the test window (e.g., some may decide days after receiving the email), the actual duration may be longer than the calculation suggests. Plan for a 1-2 week buffer if delayed conversions are common.

---

## Summary

**Cannot estimate test duration without:**
- A chosen minimum detectable effect
- A chosen confidence level
- A chosen power level

**Once these are defined**, the 4,500 weekly emails provide a solid foundation for a realistic duration estimate.
