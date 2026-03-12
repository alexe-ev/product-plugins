# Hypothesis Validation Report

## Input
Hypothesis (translated from Russian):
If we add personalized recommendations to the homepage and simplify catalog navigation for active buyers, we expect average check size to grow by 15%, because users will find relevant products faster.

---

## Verdict
**Valid for exploration, but NOT valid for experiment design**

---

## Main Weaknesses

1. **Multiple bundled changes** (Critical)
   - Two distinct interventions are merged into one hypothesis: (a) personalized recommendations on homepage, and (b) simplified catalog navigation
   - Cannot isolate which change drives the effect
   - Violates single-change principle required for causal inference

2. **Effect size claim is high without supporting evidence**
   - 15% uplift in average check size is substantial for a mature product
   - No basis provided for this specific threshold
   - Increases risk of false positive if experiment underpowered

3. **Causal mechanism is underspecified**
   - "Users will find relevant products faster" is plausible but not mechanistically detailed
   - Unknown whether faster discovery actually drives higher basket value vs. other factors (product quality, pricing, inventory)
   - Missing link between speed and order value

4. **Segment definition is light**
   - "Active buyers" is implied but not formally bounded
   - Unknown: definition of "active" (frequency, recency, spend threshold)
   - Unknown: platform scope (mobile, desktop, both)

---

## Improved Version

**Option A (Homepage recommendations focus):**
If we display personalized product recommendations based on purchase history on the homepage for active buyers (users with ≥2 purchases in the last 90 days), we expect average order value to increase by at least 8%, because relevant suggestions reduce search effort and increase basket size for repeat customers.

**Option B (Catalog navigation focus):**
If we simplify catalog navigation by adding faceted filters and category shortcuts for active buyers (users with ≥2 purchases in the last 90 days), we expect average order value to increase by at least 10%, because reduced navigation friction decreases time-to-product and increases cross-category discovery.

---

## Missing Information

To upgrade to "Valid for experiment design," provide:

1. **Isolation decision**: Which single change will be tested first? If both are critical, propose separate hypotheses for sequential testing
2. **Segment precision**: Exact definition of "active buyer" (purchase frequency, recency, or spend threshold)
3. **Platform scope**: Will the change apply to web, mobile, or both? Does context matter?
4. **Effect size basis**: What data supports the 8-15% uplift claim? Benchmarks, competitor analysis, user research, or internal pilot data?
5. **Success metric definition**: Confirm whether "average check size" means average order value (AOV), average items per order, or product line value
6. **Guardrails**: Identify secondary metrics to monitor (e.g., search drop-off, navigation errors, page load time)

---

## Readiness Statement

**This hypothesis is NOT ready for experiment design.** It requires isolation of the two changes into separate hypotheses and definition of effect size basis before proceeding to design-experiment-plan and estimate-sample-size. The hypothesis is promising for exploration — test one change first (likely homepage recommendations, which may have lower implementation cost) to establish whether the mechanism works at all before bundling changes.

---

## Recommendation

1. Run a **first experiment on just personalized recommendations** with a more conservative effect threshold (8%)
2. If successful, layer in **catalog navigation changes in a second experiment** to measure incremental impact
3. Only after both effects are validated should you consider a combined rollout

This sequential approach isolates the causal signal and reduces the risk of a failed experiment that conflates two untested mechanisms.
