# Experiment Plan: Personalized Product Recommendations

## Objective
Increase add-to-cart rate for logged-in users by testing personalized purchase-history recommendations against the current popularity-based system.

## Hypothesis
If we show personalized recommendations based on purchase history to logged-in users on product detail pages, we expect the add-to-cart rate to increase because recommendations aligned with individual purchase history should be more relevant and drive higher purchase intent compared to generic popularity-based suggestions.

## Variants

**Control:** Current popularity-based product recommendations

**Test:** Personalized purchase-history recommendations

## Target Audience
All logged-in users who visit a product detail page

## Primary Metric
Add-to-cart rate (number of add-to-cart actions / number of product detail page views)

## Secondary Metrics
- Revenue per session
- Click-through rate on recommendations

## Guardrails
- Page load time (must not increase by more than 200ms)
- Checkout completion rate (must not decline)

## Success Thresholds
- **Success criteria:** +5% relative increase in add-to-cart rate at 95% confidence level
- **Minimum meaningful effect:** +5% relative uplift
- **Sample size:** 30,000 users per group (60,000 total)
- **Estimated duration:** 3 weeks

## Stopping Logic
⚠️ **STATISTICAL VALIDITY RISK FLAGGED**

Your proposed stopping logic ("check results daily and stop as soon as we reach statistical significance") introduces **optional stopping or peeking**, which inflates the false positive rate and violates the integrity of the 95% confidence threshold.

**Problem:** Repeatedly checking for significance across days allows you to stop at lucky variance, treating p-values as if they were not sequential, which increases Type I error (false positives) well beyond your claimed 95% confidence.

**Recommended corrective actions:**

1. **Commit to full 3-week runtime:** Run the test for the entire pre-defined 3 weeks, then analyze once at the end. This preserves the 95% confidence guarantee.

2. **If early stopping is critical:** Use sequential testing with pre-defined stopping boundaries (e.g., O'Brien-Fleming boundaries) that account for multiple looks. This requires consultation with a statistician to calibrate.

3. **If daily monitoring is operational:** Establish a single, pre-defined analysis point (e.g., end of week 2, or when sample size hits 90% of target). Do not use "stop when significant."

**For this plan, recommended approach:** Commit to full 3-week runtime with a single analysis point at completion, unless a severe safety guardrail breach (e.g., page load time increasing by >500ms) requires manual shutdown.

## Randomization
⚠️ **RANDOMIZATION VALIDITY RISK FLAGGED**

Your proposed randomization by session ID introduces a critical validity threat: **the same user may be assigned to different variants across separate sessions**, violating the independence assumption required for valid inference.

**Problem:** If User A visits on Monday in the control group and returns on Wednesday, they may be assigned to the test group. This violates unit-of-randomization consistency and inflates variance, making it harder to detect true effects. It also introduces bias if users have strong session-to-session loyalty patterns.

**Recommended corrective actions:**

1. **Preferred:** Switch to user-level randomization. Extract user IDs from your pipeline and randomize by `user_id`. This ensures consistency and is worth the engineering lift.

2. **If user-level randomization is truly infeasible:** Implement session-level randomization with a persistent session cookie tied to the user. Ensure that once a user is assigned to a variant, they always see that variant on subsequent visits. Document the potential for repeat-visitor bias in the analysis plan.

3. **At minimum:** Clarify the expected proportion of users with multiple sessions during your 3-week window and quantify the bias risk in your analysis plan.

**For this plan, recommended approach:** Use user-level randomization if feasible within 1-2 weeks of implementation. If not possible, use persistent session randomization with bias risk documentation.

## Analysis Plan

1. **Stratification:** If randomization remains session-based, stratify post-hoc analysis by user repeat-visit frequency to assess bias.
2. **Primary analysis:** Compare add-to-cart rates between control and test groups using a two-sample proportions test.
3. **Guardrail analysis:** Monitor page load time (mean difference) and checkout completion rate (proportion test) to flag negative impacts.
4. **Secondary metrics:** Analyze revenue per session and recommendation CTR as supporting indicators.

## Decision Rules

**If +5% or greater uplift in add-to-cart rate with 95% confidence and guardrails healthy:**
→ Ship the personalized recommendations.

**If positive uplift but below +5% threshold:**
→ Iterate on the recommendation algorithm or run a larger follow-up test.

**If negative impact on add-to-cart rate or guardrails breached:**
→ Reject the change and return to popularity-based recommendations.

## Launch Readiness Checklist

✓ Hypothesis clearly defined
✓ Variants specified
✓ Target segment defined
✓ Primary metric defined
✓ Success threshold defined
✓ Sample size and duration defined
✓ Guardrails defined

⚠️ Stopping logic requires revision (remove daily peeking)
⚠️ Randomization method requires revision (user-level preferred)

**Plan Status:** Structurally complete but execution-blocked until stopping logic and randomization method are resolved.

---

## Summary of Required Fixes Before Launch

1. **Stopping logic:** Commit to full 3-week runtime with analysis at completion, or implement pre-defined sequential boundaries. Do not allow daily peeking.
2. **Randomization:** Switch to user-level randomization, or implement persistent session-level randomization with bias risk documentation.
