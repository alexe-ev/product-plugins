# Sample Size Estimation: Food Delivery App Restaurant Card Design

## Executive Summary

For your A/B test on the new restaurant card design, you need approximately **18,439 users per variant** (36,877 total). With 35,000 eligible users per week, this test can run in approximately **1.05 weeks (7.4 days)**.

---

## Calculation Details

### Inputs Provided
- **Primary metric type:** Conversion / click-to-order rate
- **Baseline conversion rate (p1):** 7.8%
- **Minimum detectable effect:** +0.8 percentage points (absolute)
- **Target conversion rate (p2):** 8.6% (7.8% + 0.8%)
- **Confidence level:** 95% (two-sided)
- **Statistical power:** 80%
- **Eligible traffic:** 35,000 users per week
- **Split ratio:** 50/50

### Z-Values Used
- z_α/2 (95% confidence, two-sided) = 1.96
- z_β (80% power) = 0.84
- (z_α/2 + z_β)² = (1.96 + 0.84)² = 2.8² = **7.84**

### Explicit Formula Applied

Using the conversion metric formula from the experimentation reference:

```
n_per_group = (z_α/2 + z_β)² × (p1×(1−p1) + p2×(1−p2)) / (p2 − p1)²
```

### Step-by-Step Calculation

**Step 1:** Calculate variance components
- p1×(1−p1) = 0.078 × (1 − 0.078) = 0.078 × 0.922 = **0.071916**
- p2×(1−p2) = 0.086 × (1 − 0.086) = 0.086 × 0.914 = **0.078604**

**Step 2:** Sum variance components
- 0.071916 + 0.078604 = **0.150520**

**Step 3:** Calculate numerator
- 7.84 × 0.150520 = **1.180077**

**Step 4:** Calculate effect size squared
- (p2 − p1)² = (0.086 − 0.078)² = 0.008² = **0.000064**

**Step 5:** Calculate sample size per group
- n_per_group = 1.180077 / 0.000064 = **18,439 users**

**Step 6:** Calculate total sample size
- Total = 18,439 × 2 = **36,877 users**

**Step 7:** Estimate duration
- Duration = 36,877 / 35,000 per week = **1.05 weeks** (approximately 7.4 days)

---

## Results

### Sample Size Estimates

| Metric | Value |
|--------|-------|
| Sample size per group | 18,439 users |
| Total sample size | 36,877 users |
| Estimated test duration | 1.05 weeks (7.4 days) |
| Traffic saturation | 94.9% of weekly eligible traffic |

---

## Assumptions Used

1. **Two-variant A/B test** with fixed-horizon design (test runs for the full duration)
2. **Stable traffic quality** across the test period—no major shifts in user behavior, device type, or geography
3. **No compound effects** from promotions, campaigns, or platform-wide launches during the test
4. **Eligible traffic** refers to users who actually reach the restaurant browsing surface where the new card design is tested
5. **Users are assigned once** and remain in their variant for the entire test period
6. **No interaction effects** between variants (e.g., network effects from other users seeing the design)

---

## Feasibility Assessment

✓ **Test is highly feasible**

- **Timeline:** 7.4 days is a short, actionable test window. You can iterate quickly and make launch decisions within a week.
- **Traffic sufficiency:** Your 35,000 weekly eligible users exceed the required 36,877 total sample by 94.9%, meaning you'll reach required sample size in just over one week.
- **Statistical power:** At 80% power, you have a 4 in 5 chance of detecting a true +0.8pp uplift if it exists.
- **Effect size reasonability:** A +0.8pp absolute uplift (10% relative improvement) is meaningful for a product change and justifiable as a minimum effect to detect.

---

## Caveats and Considerations

### If Weekly Traffic Varies
The duration estimate assumes stable 35,000 eligible users per week. If your traffic fluctuates seasonally:
- **Higher traffic weeks:** Test will complete faster
- **Lower traffic weeks:** Test will need to extend; consider running the test over a full calendar week or two to smooth variation

### If Eligible Traffic Definition Changes
If "eligible traffic" changes—for example, if more users are added or removed from the test audience mid-run—duration will shift. Validate that all users who browse restaurants are actually eligible.

### If Conversion Rate Differs from Baseline
The sample size is calibrated to baseline 7.8%. If your actual baseline is materially different (e.g., 5% or 10%), the sample size calculation should be re-run.

### Multiple Testing / Secondary Metrics
This calculation covers your primary metric only. If you are testing secondary metrics as well, you may need additional sample size for secondary metric power.

---

## Recommendation

Proceed with this A/B test design. You have:
- ✓ Clear primary metric
- ✓ Specific, quantified baseline and MDE
- ✓ Sufficient weekly traffic to complete the test in ~1 week
- ✓ Reasonable statistical rigor (95% confidence, 80% power)

Plan to monitor results after 7–10 days. By that point you should have sufficient data to make a confident launch decision.

---

## Next Steps

1. **Confirm eligible traffic definition:** Validate that 35,000/week reflects the true number of unique users who browse restaurant cards in your app.
2. **Check for seasonality:** If you're running this during a high- or low-demand period, adjust the expected duration.
3. **Define winning threshold:** Agree in advance whether you will declare a winner on primary metric alone, or require consistency across secondary metrics.
4. **Prepare diagnostics:** Plan to monitor:
   - Assignment balance (50/50 split confirmed)
   - Traffic stability across days
   - Any anomalies in conversion timing or user segment makeup
