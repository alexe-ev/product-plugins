# Experiment Hypothesis Formulation

**Input Context (translated from Russian):**
- Product: Used electronics marketplace
- Current mobile web conversion (product card → purchase): 3.2%
- Proposed changes: (1) add seller video reviews to product cards, (2) reduce checkout from 4 to 2 steps
- Target segment: Android smartphone buyers
- Target outcome: raise conversion to 5%

---

## Analysis

### Context Assessment
This input is **context-rich**:
- Clear product area (product card and checkout funnel)
- Specific segment identified (Android mobile web users)
- Known current metric (3.2% conversion)
- Known target outcome (5% conversion)
- Business goal is explicit (improve conversion)

### Critical Issue: Bundled Interventions
The user has proposed **two independent product changes simultaneously**:
1. Add seller video reviews to product cards
2. Reduce checkout steps from 4 to 2

**Per skill instruction #8:** When multiple changes are mixed together, split them into separate hypotheses.

Bundling these interventions has several drawbacks:
- Impossible to isolate which change caused results
- Can't learn independently from each intervention
- Video reviews and checkout friction address different funnel stages
- If only one intervention is effective, bundling masks that learning

**Recommendation:** Test these as two separate experiments to identify which (or both) drives conversion lift.

---

## Hypothesis 1: Seller Video Reviews

### Hypothesis Statement
If we add seller-recorded video reviews to product cards for Android mobile web users in the used electronics category, we expect the product card-to-purchase conversion rate to increase, because video builds social proof and reduces trust uncertainty around used items.

### Target Segment
Android smartphone buyers browsing used electronics on mobile web.

### Likely Primary Metric
Conversion rate: completed purchases / product card views (currently 3.2%)

### Expected Direction of Impact
Increase (video reviews reduce friction from trust/uncertainty)

### Why This Might Work
- Used electronics carry higher trust risk than new items
- Video from actual seller is stronger social proof than text reviews
- Mobile-first users are visual learners; video plays to platform strength
- Short-form seller video can address top purchase hesitations (condition, functionality)

### Expected Impact Hypothesis
**No quantitative assumption provided.** The user stated a target of 5% but did not provide evidence (prior test results, industry benchmarks, or documented rationale) linking video reviews specifically to that lift. Video review impact will depend on adoption rate, video quality, and content quality—all unknowns at hypothesis stage.

### Missing Information
- What fraction of sellers will actually provide video reviews?
- What is typical video completion/engagement rate on mobile?
- Are there prior benchmarks for video review impact on used-goods conversion?
- Will video reviews be mandatory or optional for sellers?

### Confidence Level
**Context-informed**

Core inputs are present (change: video reviews; segment: Android mobile; metric: conversion rate; direction: increase). However, adoption mechanics and video content quality are not yet defined, so hypothesis can move to validation but should validate video review feasibility first.

---

## Hypothesis 2: Streamlined Checkout Flow

### Hypothesis Statement
If we reduce the checkout flow from 4 steps to 2 for Android mobile web users purchasing used electronics, we expect the product card-to-purchase conversion rate to increase, because fewer friction points reduce cart abandonment and cognitive load.

### Target Segment
Android smartphone buyers completing purchases on mobile web.

### Likely Primary Metric
Conversion rate: completed purchases / product card views (currently 3.2%)

### Expected Direction of Impact
Increase (reducing checkout steps decreases friction)

### Why This Might Work
- Mobile checkout is inherently friction-laden; each step increases abandonment risk
- 4-step flow is verbose; 2-step streamlines to essentials (shipping + payment, for example)
- On small screens, fewer page transitions reduce cognitive load and user error
- Used goods buyers may be price-sensitive and more likely to abandon on friction

### Expected Impact Hypothesis
**No quantitative assumption provided.** The user stated a target of 5% but did not provide evidence for checkout step reduction specifically. Actual lift depends on which steps are removed, payment completion rates, and error handling—not yet detailed.

### Missing Information
- Which steps will be removed or consolidated?
- How is data (address, payment) being combined or pre-filled?
- Will this impact checkout completion rate or introduce new error points?
- Any prior test data on step reduction in similar products?
- Will users need to confirm consolidated information before payment?

### Confidence Level
**Context-informed**

Core inputs are clear (change: 2-step checkout; segment: Android mobile; metric: conversion; direction: increase). However, the specific mechanics of the 2-step flow (e.g., which fields are combined, how pre-fill logic works) are not yet designed, so this requires clarification before moving to experiment design.

---

## Recommendation for Next Steps

### Option A: Run Both Tests Sequentially (Recommended)
1. **Test Hypothesis 1 first** (video reviews) — typically lower engineering lift; results in 2–3 weeks
2. **If video reviews show lift**, run Hypothesis 2 (checkout streamline) to compound gains
3. **If video reviews show no lift**, focus resources on Hypothesis 2

### Option B: Run Both Tests in Parallel
- Requires larger sample sizes to maintain statistical power
- Acceptable if both teams can execute independently
- Faster learning but higher resource cost

### Option C: Run a Combined Test (Not Recommended)
- If both features are already built and must ship together, test as a single bundle
- Accept that you cannot isolate which driver is responsible
- Use this data to inform which feature to optimize or iterate next

### Before Proceeding to Validation:
1. **Clarify checkout flow design** — specifically, which fields/steps will be consolidated
2. **Determine video review adoption strategy** — will it be mandatory, optional, or initially seeded by team?
3. **Confirm primary metric definition** — is this conversion at product card view, or at some other stage (e.g., add-to-cart)?
4. **Validate that 5% is achievable** — what historical context suggests this is realistic from video + checkout alone?

---

## Summary Table

| Element | Hypothesis 1: Video Reviews | Hypothesis 2: Checkout Streamline |
|---------|-------|-------|
| **Change** | Add seller video reviews to product cards | Reduce checkout from 4 steps to 2 |
| **Segment** | Android mobile, used electronics category | Android mobile, at checkout |
| **Primary Metric** | Conversion rate (card → purchase) | Conversion rate (card → purchase) |
| **Expected Direction** | Increase | Increase |
| **Mechanism** | Trust + social proof reduce hesitation | Fewer steps reduce friction & abandonment |
| **Confidence** | Context-informed | Context-informed |
| **Next Action** | Validate video adoption and engagement | Design and validate 2-step flow mechanics |

---

**Output Generated:** 2026-03-11
**Skill Applied:** formulate-experiment-hypothesis (following all 10 instructions and 8 caveats)
