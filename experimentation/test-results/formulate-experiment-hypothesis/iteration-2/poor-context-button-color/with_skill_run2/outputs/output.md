# Experiment Hypothesis Formulation: Button Color Change for Conversion Lift

## Input Analysis
User input (translated from Russian):
"Conversion is falling, we need to do something. We think about changing the button color. This should raise conversion by 30%."

## Context Level Assessment
**Provisional** — This input exhibits significant context gaps. The specific product area, affected user segment, primary metric definition, and causal rationale are all unclear or unconfirmed. The 30% uplift claim has no documented evidence basis.

---

## What is Known
- There is a conversion decline (direction and magnitude unconfirmed)
- A button color change is being considered as a solution
- The team has an expectation of 30% uplift

## What is Assumed
- Nothing reliable; the input is largely intuitive

## What Must Be Confirmed

Before a testable hypothesis can be written, the following must be clarified:

1. **What product area is changing?**
   - Which button? (CTA, checkout, signup, payment, form submission, etc.)
   - What is its primary purpose in the user flow?

2. **Which users are affected?**
   - Is this change for all users, new users, returning users, or a specific cohort?
   - Is there a geographic, device, or acquisition-channel segment?

3. **What metric are we actually tracking?**
   - Conversion of what? (page-to-page, funnel stage, transaction, signup, etc.)
   - Is "conversion" already tracked and measured in your system?

4. **What problem are we solving?**
   - Is the conversion decline recent or trending? How severe?
   - Has the team identified why conversion is falling (UI, copy, targeting, external factors)?
   - Is button color a hypothesis based on user research, A/B test history, or intuition?

5. **What is the baseline or benchmark?**
   - What is the current conversion rate?
   - Has button color been tested before in this product?

---

## Provisional Hypothesis (Not Yet Validated)

**If we change the button color for [unspecified users],**
**we expect [primary metric] to increase,**
**because a different color may improve visual prominence or trigger different user behavior.**

This is a placeholder and cannot move forward without resolving the missing context above.

---

## Critical Issue: Impact Assumption

**Flag:** The user states the change "should raise conversion by 30%." This claim has **no evidence basis** documented in the input.

Per skill instructions, we do not adopt unsupported numerical uplift assumptions. The 30% figure is:
- Not tied to prior test results
- Not tied to industry benchmarks
- Not tied to documented research or qualitative insights
- Presented as intuition

**Action:** Do not include an "Expected impact hypothesis" at this stage. Instead, flag under Missing information.

---

## Missing Information

Before this hypothesis can be execution-ready, confirm:
1. Which specific button is being changed (and why this particular one)?
2. The exact product area and user funnel (e.g., checkout, signup, feature adoption)
3. Target segment (new users, returning users, all users, specific cohort?)
4. Current conversion rate and trend (how far is it falling?)
5. Primary outcome metric (clearly defined and measured)
6. Rationale for button color as the intervention (user research, prior tests, design principle?)
7. Why 30% uplift is expected (prior results, industry benchmark, or other evidence)
8. Whether this is a full-traffic change or a segment-level experiment

---

## Discovery Questions to Resolve Context

To move forward, please answer at least 3 of these:

1. **What button are you changing?** (e.g., "Add to Cart," "Place Order," "Start Free Trial")
2. **What is the current conversion rate, and by how much has it declined?**
3. **What evidence suggests button color is the root cause?**
4. **Has your team tested button color changes before? If so, what were the results?**
5. **Is this change meant for all users or a specific segment (e.g., new users, mobile users, a particular market)?**

---

## Confidence Level of Hypothesis Framing

**Provisional**

The hypothesis cannot progress to execution-ready candidate status until the core inputs (specific button, specific user segment, measurable primary metric, and causal rationale) are provided.

---

## Recommended Next Steps

1. **Clarify the change:** Which button, and why is button color the hypothesized solution?
2. **Confirm the metric:** Define what "conversion" means in your system (e.g., "purchase conversion," "signup completion," "lesson start").
3. **Identify the segment:** Who is affected by this change?
4. **Validate the assumption:** Is there prior evidence (user testing, A/B results, research) that button color influences this metric?
5. **Resubmit with enriched context** to re-run the formulate-experiment-hypothesis skill.

---

## Downstream Handoff Readiness

This output is **not yet ready** to hand off to:
- `validate-hypothesis-quality` (hypothesis is too vague)
- `define-success-metrics` (primary metric is unconfirmed)
- `design-experiment-plan` (segment, baseline, and causal rationale are missing)

Resolve missing context first, then re-run this skill with enriched input.
