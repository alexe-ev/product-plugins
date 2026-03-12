# Experiment Hypothesis Formulation: Button Color Change

## Input Summary
**Original input:** "Conversion is falling, we need to do something. We're thinking of changing the button color. This should raise conversion by 30%."

**Context level:** Context-poor with forced numerical assumption

---

## Discovery: Missing Critical Context

Before proceeding to a hypothesis, the following critical details must be clarified:

### Missing Information
1. **Product area**: Which product, funnel, or page are we talking about?
2. **Specific button**: Which button (CTA, checkout, sign-up, etc.)?
3. **Current button color**: What is it now?
4. **Proposed button color**: What are we changing it to, and why this color specifically?
5. **Target segment**: All users, new users, returning users, a specific cohort?
6. **Time period**: When did conversion start falling? Over what period?
7. **Baseline metrics**: What is the current conversion rate? By what percentage has it fallen?
8. **Why button color**: What user research or observation suggests button color is the root cause?
9. **Primary metric**: Is it funnel completion rate, purchase conversion, sign-up rate, or something else?

---

## Provisional Hypothesis (Data-Informed, Not Confidence-Ready)

Based on minimal available input, here is a provisional hypothesis structure:

**If we change [button color] for [all users / specific segment],**
**we expect [primary conversion metric] to [increase],**
**because [color may affect visual hierarchy, contrast, or call-to-action salience].**

---

## Key Problems with the Input

### Problem 1: Forced Numerical Assumption
**The claim that button color change will "raise conversion by 30%" is:**
- Unsupported by typical color-change research
- Inconsistent with typical A/B test effect sizes for UI changes
- Potentially dangerous if used to set success criteria
- **Action**: Do NOT use 30% as a success threshold or expected impact
- Typical button color tests show 2–15% impact when there is clear usability/contrast improvement, and often show negligible or no statistical significance

### Problem 2: Causality Unknown
The input asserts that a color change will solve a conversion decline, but:
- No root cause analysis has been done
- Conversion could be declining due to traffic quality, market conditions, product changes, or funnel friction elsewhere
- A button color change may not address the real problem

### Problem 3: Vague Intervention
"Change button color" is under-specified:
- No current color stated
- No target color stated
- No rationale for the color choice
- Higher-impact changes (button copy, button placement, form simplification) were not mentioned

---

## Recommended Hypothesis (Pending Context)

Once the missing information is provided, the hypothesis should follow this pattern:

**If we change the [button name/color] from [current] to [proposed] for [segment],**
**we expect [specific metric] to [increase/decrease],**
**because [specific causal reason: contrast, visual hierarchy, urgency signal, etc.].**

### Example (with real context):
- **If** we change the checkout button color from gray to high-contrast green for all desktop users,
- **we expect** primary conversion rate to increase,
- **because** higher contrast and warm color may draw more visual attention to the main CTA.

---

## Expected Impact Hypothesis

**Status**: Not set at this stage.

Reason: No validated basis exists for claiming a 30% uplift from a button color change alone. Once the experiment is designed and runs, the actual impact can be measured. Typical color/contrast changes show effects in the range of:
- No significant impact (55% of cases)
- 1–5% improvement (30% of cases)
- 5–15% improvement (15% of cases)
- Rare: >15% improvement

**Do not use the 30% claim as a success metric or hypothesis basis.**

---

## Missing Information Checklist

Before proceeding to experiment design, resolve these:

- [ ] Confirm the product area and funnel stage affected
- [ ] Identify the specific button and its current color
- [ ] Define the proposed color and rationale
- [ ] Specify the target segment
- [ ] Confirm the primary metric (e.g., checkout completion rate, sign-up rate)
- [ ] Establish baseline conversion rate
- [ ] Root-cause analysis: Why do we think button color is the issue?
- [ ] Any user research or qualitative insights supporting the hypothesis?

---

## Confidence Level

**Status**: **Provisional**

**Reasoning**:
- The input lacks sufficient product context
- The numerical claim (30%) is unsupported and should be discarded
- The intervention (button color) may or may not be the root cause of the conversion decline
- This hypothesis cannot move to execution-ready status until the missing context is filled in

---

## Downstream Handoff

Once the above context is collected, this skill's output can be passed to:
1. **validate-hypothesis-quality** – to check internal logic
2. **define-success-metrics** – to set realistic success thresholds (NOT 30%)
3. **design-experiment-plan** – to plan sample size, duration, and segments

**Critical note for next steps**: Do not accept the 30% uplift claim. Set success metrics based on historical effect sizes and business need, not on unsupported predictions.

---

## Key Recommendation

Before running this experiment:
1. Conduct a brief root-cause analysis: Is conversion really falling due to button visibility, or is it due to traffic quality, funnel friction, or market changes?
2. Review user feedback and session recordings if available.
3. Reframe the hypothesis based on actual observations, not assumptions.
4. Set a realistic success threshold (e.g., statistically significant increase, not a fixed 30%).
