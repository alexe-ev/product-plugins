# A/B Test Duration Estimate: Trial Expiry Email Sequence

## Given Information
- **Current conversion rate (baseline):** 12.3%
- **Weekly email volume:** 4,500 trial expiry emails
- **Test setup:** Control (current design) vs. Treatment (new design), 50/50 split

---

## Key Challenge: Missing Critical Inputs

To accurately estimate test duration, we need three critical parameters that weren't specified:

### 1. **Minimum Detectable Effect (MDE)**
This is the smallest improvement you want to reliably detect. Common choices:
- **Modest improvement:** 20% relative lift (12.3% → 14.76%) - 2.46 percentage points
- **Meaningful improvement:** 25% relative lift (12.3% → 15.375%) - 3.075 percentage points
- **Conservative target:** 30% relative lift (12.3% → 16.0%) - 3.7 percentage points

### 2. **Statistical Confidence Level**
The probability of avoiding Type I errors (false positives):
- **Standard choice:** 95% confidence (α = 0.05)
- **Conservative choice:** 99% confidence (α = 0.01)

### 3. **Statistical Power**
The probability of detecting the effect if it truly exists (avoiding Type II errors):
- **Standard choice:** 80% power (β = 0.20)
- **Higher power:** 90% power (β = 0.10)

---

## Sample Size Calculations

### Scenario Analysis

Using the standard formula for proportions in A/B testing:

**n = 2 × (Z_α/2 + Z_β)² × [p₀(1-p₀) + p₁(1-p₁)] / (p₁ - p₀)²**

Where:
- n = sample size per variation
- p₀ = baseline conversion rate (0.123)
- p₁ = expected conversion rate under treatment
- Z_α/2 = critical value for confidence level
- Z_β = critical value for power

### Scenario 1: 20% MDE, 95% Confidence, 80% Power
- Target: 14.76% conversion (0.246 pp improvement)
- Sample size needed per variation: **~3,600 conversions**
- Total conversions needed: **7,200**
- Expected duration: **~1.6 weeks**

### Scenario 2: 25% MDE, 95% Confidence, 80% Power (RECOMMENDED)
- Target: 15.375% conversion (0.3075 pp improvement)
- Sample size needed per variation: **~2,300 conversions**
- Total conversions needed: **4,600**
- Expected duration: **~1 week**

### Scenario 3: 30% MDE, 95% Confidence, 80% Power
- Target: 16.0% conversion (0.37 pp improvement)
- Sample size needed per variation: **~1,600 conversions**
- Total conversions needed: **3,200**
- Expected duration: **~0.7 weeks**

### Scenario 4: 20% MDE, 95% Confidence, 90% Power
- Target: 14.76% conversion (0.246 pp improvement)
- Sample size needed per variation: **~4,700 conversions**
- Total conversions needed: **9,400**
- Expected duration: **~2.1 weeks**

---

## Conversions vs. Email Volume

**Important distinction:**
- 4,500 emails/week ≠ 4,500 conversions/week
- With 12.3% baseline conversion, you expect ~553 conversions per week
- Each scenario's duration is based on the conversion target, not email volume

---

## Recommended Approach

Given your business context, I recommend:

### **Default Recommendation: 20-25% MDE, 95% Confidence, 80% Power**
- **Test duration:** 1-2 weeks
- **Why this range:**
  - 1 week is likely too optimistic (relies on tighter effect size)
  - 2-3 weeks accounts for natural variation and ensures robustness
  - Balances statistical rigor with product velocity
  - Sufficient power to detect meaningful business impact

### **Next Steps to Finalize Duration:**

1. **Define your MDE:** What's the smallest improvement that would justify deploying the new email design?
   - Consider: Cost of email design iteration, implementation effort, opportunity cost
   - If unsure, 25% relative lift is a practical middle ground

2. **Confirm confidence/power preferences:**
   - 95% confidence / 80% power is industry standard
   - Choose 90% power only if Type II errors are costly

3. **Account for practical factors:**
   - **Sequential testing:** Can stop early if effect is clear (reduces duration ~20%)
   - **Weekly cadence:** Results align with weekly reporting cycles
   - **Seasonality:** Any week-to-week variations in trial signups could affect accuracy

---

## Risk Considerations

- **Under-powered test:** Running <1 week risks failing to detect real improvements
- **Over-powered test:** Running >4 weeks may waste time on clear winners/losers
- **Sample ratio mismatch:** Ensure 50/50 control/treatment split is maintained
- **Novelty effects:** New design may have temporary boost or friction — consider longer observation period

---

## Summary Table

| Scenario | MDE | Duration | Sample Size | Risk Level |
|----------|-----|----------|------------|-----------|
| Conservative | 20% | 1.6 wks | 7,200 conv | Low - robust |
| **Recommended** | **25%** | **~1 wk** | **4,600 conv** | **Balanced** |
| Aggressive | 30% | 0.7 wks | 3,200 conv | High - less robust |

---

## Conclusion

**For a statistically sound result with your current volume, plan for 1-2 weeks of testing.** This assumes:
- You're targeting a 25% relative improvement (3.1pp absolute lift)
- You want 95% confidence and 80% power
- You maintain consistent traffic patterns

To finalize this estimate, specify your desired MDE and we can calculate the exact duration. If you want results in 3-5 days, you'd need to either increase traffic to the test or reduce your statistical confidence.
