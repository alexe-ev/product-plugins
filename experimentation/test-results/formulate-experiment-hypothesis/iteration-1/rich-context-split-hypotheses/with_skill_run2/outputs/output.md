# Experiment Hypotheses: Used Electronics Marketplace

## Context Summary
- **Product:** Used electronics marketplace
- **Current baseline:** 3.2% conversion rate (product card → purchase) on mobile web
- **Target segment:** Android smartphone buyers
- **Goal:** Increase conversion to 5% (56% uplift)
- **Proposed changes:** (1) Add seller video reviews to product card; (2) Reduce checkout from 4 steps to 2

---

## Analysis Note
The input describes two independent product changes. Per best practice, these should be tested as separate hypotheses to isolate which intervention drives impact, rather than bundling them into a single test. This allows the team to understand the individual contribution of each change and apply learnings more precisely.

---

## Hypothesis 1: Seller Video Reviews on Product Card

**Hypothesis:**
If we add seller video reviews to the product card for Android smartphone buyers on mobile web,
we expect conversion rate to increase,
because social proof in the form of seller video reviews reduces purchase anxiety and provides additional credibility signals before checkout.

**Target segment:**
Android smartphone buyers viewing product cards on mobile web

**Likely primary metric:**
Conversion rate (product card view → purchase completion)

**Expected direction:**
Increase

**Why this might work:**
- Video content provides richer, more persuasive proof than static product images alone
- Sellers demonstrating the product in use builds trust, especially in the used electronics category where condition and functionality are primary concerns
- Video reduces friction by answering common questions before the user enters checkout
- Social proof is particularly effective for used goods where authenticity concerns are high

**Expected impact hypothesis:**
Unknown without prior testing; the 56% uplift (3.2% → 5%) may be shared across both interventions. Video alone may contribute 1-2 percentage points if it successfully converts browsers who are currently hesitant.

**Missing information:**
- Video hosting and production strategy (user-generated, edited, moderated?)
- Whether video placement on card affects card load time or mobile UX
- Baseline video completion rates for this audience
- Whether sellers have sufficient video content available
- Any existing user research on video preference for used electronics category

**Confidence level of framing:**
Context-informed
(The problem is clear, the segment is specific, the mechanism is plausible, but the expected uplift is not derived from research or prior data.)

---

## Hypothesis 2: Checkout Reduction (4 Steps → 2 Steps)

**Hypothesis:**
If we reduce checkout from 4 steps to 2 for Android smartphone buyers on mobile web,
we expect conversion rate to increase,
because reducing friction at the point of purchase removes abandonment triggers in the checkout funnel.

**Target segment:**
Android smartphone buyers completing checkout on mobile web

**Likely primary metric:**
Conversion rate (product card view → purchase completion)
OR
Checkout completion rate (checkout start → purchase confirmation)

**Expected direction:**
Increase

**Why this might work:**
- Mobile checkout is particularly sensitive to friction; each additional step creates abandonment opportunity
- Consolidating steps likely reduces perceived effort and cognitive load
- Fewer form submissions = fewer technical failures on mobile networks
- Fewer steps may also improve mobile UX by reducing page load and re-rendering cycles
- The 4-to-2 step reduction is a 50% friction decrease, which is material

**Expected impact hypothesis:**
Unknown without prior testing; the 56% uplift may be shared across both interventions. Checkout reduction may contribute 2-3 percentage points if it meaningfully addresses drop-off in the current 4-step flow.

**Missing information:**
- Current step-by-step abandonment rates in the 4-step checkout
- Which steps are being consolidated and how (e.g., payment + billing address combined?)
- Whether 2-step flow meets compliance or payment processor requirements
- Expected increase in cart abandonment if checkout is perceived as "too fast" or incomplete
- Whether Android users have different abandonment patterns than iOS users in the current flow

**Confidence level of framing:**
Context-informed
(The problem is clear and common in mobile commerce, the segment is specific, the mechanism is sound, but the expected uplift is not derived from current funnel data.)

---

## Recommendations for Experiment Design

### Option A: Run Sequentially
Test checkout reduction first (typically higher impact and lower risk), then layer video reviews to measure incremental gain.

### Option B: Run as 2x2 Factorial
- Control: Current state (no video, 4-step checkout)
- Test A: Video only
- Test B: Checkout reduction only
- Test C: Both video + checkout reduction

**Advantages:** Understand individual and combined effects, may reach 5% goal in Test C.
**Disadvantage:** Requires larger sample size.

### Option C: Run Sequentially, Then Combined
Test video first, then checkout second. If results are positive and additive, you may reach the 5% goal. If not, avoid the 2x2 overhead.

---

## Next Steps

1. **Validate hypothesis quality** – Ensure both hypotheses are specific and measurable before experiment design
2. **Define success metrics** – Establish primary metric, secondary metrics, and guardrails (e.g., don't harm average order value, don't increase support tickets)
3. **Estimate sample size** – Determine if the Android segment has sufficient traffic to detect a meaningful difference in the 56-session window
4. **Resolve missing context** – Collect checkout funnel data, video availability, and any prior mobile optimization results
5. **Design experiment plan** – Choose sequential vs. factorial approach and lock in traffic allocation, duration, and stopping criteria
