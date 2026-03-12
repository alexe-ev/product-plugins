# Hypothesis Validation Report

## Input Hypothesis
If we add personalized recommendations on the homepage and simplify catalog navigation for active buyers, we expect a growth in average check of 15%, because users will find relevant products faster.

## Verdict
**Valid for exploration, NOT valid for experiment design**

---

## Analysis

### Main Weaknesses

1. **Mixed changes bundled together**: The hypothesis combines two distinct interventions—personalized recommendations AND simplified navigation—into a single test. These should be evaluated separately to isolate causal attribution.

2. **Ambiguous segment definition**: "Active buyers" is implied but not precisely bounded. Does it mean:
   - Purchased within the last 30/60/90 days?
   - A specific cohort by purchase frequency?
   - A revenue tier?
   - This lack of precision makes reproducibility difficult.

3. **Primary metric definition is unclear**: "Average check" is likely average order value (AOV), but the exact formula is not stated:
   - Total order value / number of orders?
   - For a specific time window?
   - Including or excluding returns/cancellations?
   - Across all categories or specific categories only?

4. **Implausibly high effect size without supporting evidence**: A 15% uplift on AOV is a strong claim without prior data:
   - If this is a mature product with existing recommendations/navigation, 15% is a red flag
   - If this is a new feature, prior A/B test data or cohort analysis should justify the expectation
   - No baseline, no supporting evidence provided

5. **Causal mechanism is incomplete**: The reasoning states "users will find relevant products faster," but doesn't explain the path to 15% higher AOV:
   - Does faster discovery lead to more items per order (quantity)?
   - Or higher-priced items (mix shift)?
   - Or simply more conversions at existing AOV?
   - The link between "faster discovery" and "15% higher check" is assumed, not established.

---

## Improved Version

To split into testable hypotheses and add missing structure:

**Hypothesis 1 (Personalized Recommendations):**
If we add personalized product recommendations to the homepage for customers who have made at least 2 purchases in the last 90 days, we expect the average order value of their next purchase to increase by at least 8%, because recommendations will surface higher-value items relevant to their purchase history.

**Hypothesis 2 (Simplified Navigation):**
If we reduce the catalog navigation menu depth from 4 levels to 2 levels for active buyers (2+ purchases in last 90 days), we expect the average order value to increase by at least 5%, because reduced friction will allow customers to discover and add complementary products more quickly.

*Rationale for changes:*
- Separated the two changes to enable isolated testing and clear attribution
- Defined "active buyers" explicitly (2+ purchases in 90 days)
- Specified the metric formula (AOV of next purchase)
- Lowered and differentiated expected uplift to match the specific intervention (8% vs. 5% instead of bundled 15%)
- Clarified the causal path for each change
- Made segment and measurement reproducible

---

## Missing Information for Experiment Design

1. **Baseline data**: Historical AOV for the active buyer segment. Is the current AOV €50, €500, or €5,000? Baseline context is critical to assess whether 15% (or even 8%/5%) is plausible.

2. **Segment size & traffic volume**: How many "active buyers" do you have daily/weekly? Is the segment large enough to achieve statistical significance in a reasonable test window?

3. **Prior test results**: Have similar recommendations or navigation changes been tested before? What were the results? (This informs effect size credibility.)

4. **Success threshold (guardrails)**: Beyond AOV, what should NOT change?
   - Conversion rate (should not drop)?
   - Return/cancellation rate (should not increase)?
   - Cart abandonment (should not worsen)?

5. **Revenue or business constraint**: Is a 15% uplift the target, or is there a lower threshold that would still be considered a win? (E.g., "at least 3% is meaningful given our margin structure.")

6. **Technical dependencies**: Are recommendations and navigation simplified already built, or does this require development? This affects test timeline and feasibility.

---

## Readiness Statement

**This hypothesis is NOT ready for experiment design.** It combines two changes that must be tested separately, lacks precise segment and metric definitions, and the 15% effect size is not credible without supporting baseline or prior test data. Before proceeding to define-success-metrics or estimate-sample-size:

1. Split into two separate, single-change hypotheses
2. Define active buyers by explicit cohort rules (e.g., 2+ purchases in 90 days)
3. Specify AOV calculation (e.g., "revenue per order, excluding returns, for the 14 days after the change goes live")
4. Lower expected effect magnitude to 8% or below and justify with baseline data or analogous prior results
5. Gather baseline AOV and segment size to assess statistical feasibility

Once these changes are made, the revised hypotheses will be valid for experiment design.

---

## Context Assessment

**Input context level:** Light
**Required for approval:** Medium (baseline metrics, segment definition, separated changes)

The hypothesis shows good intent and identifies a plausible direction (discovery friction + recommendations → higher order value), but the bundling, vague definitions, and unsupported effect size prevent advancement to the next phase. This is a common stage—the next step is refinement, not experiment launch.
