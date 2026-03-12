# Hypothesis Validation Analysis

## Input
Hypothesis (translated from Russian):
"If we add a push notification reminder about an abandoned cart 1 hour after abandonment for all mobile users, we expect a 25% increase in completed orders, because users often get distracted and forget to return."

---

## Verdict
**Valid for exploration** — the direction is promising and the hypothesis is testable, but the expected effect size raises structural concerns that require additional context before proceeding to formal experiment design.

---

## Main Weaknesses

1. **Implausibly high effect magnitude without supporting data**
   - A 25% relative uplift in order completion is ambitious for a single-touch intervention on a mobile-only audience
   - Most cart abandonment interventions in mature e-commerce settings show 3–8% recovery rates (not uplift on completed orders overall)
   - The claim lacks evidence or benchmarking; it may confuse local recovery rate with global order completion uplift

2. **Causal claim is overstated but not wrong**
   - The mechanism "users get distracted and forget" is plausible, but underspecified
   - The 1-hour timing is mentioned but not justified; no evidence it is optimal
   - The hypothesis does not account for potential downsides (notification fatigue, opt-out effects)

3. **Primary metric is ambiguous**
   - "Completed orders" — does this mean orders completed by previously-abandoning users (recovery), or global order count?
   - If recovery: measure should be "abandoned cart recovery rate" or "re-engagement conversion on push recipients"
   - If global: the connection is too indirect; push to abandoned carts should not move the total order count by 25%

4. **Segment is partially defined**
   - "All mobile users" is clear in scope but may be too broad
   - The hypothesis targets users who abandon carts, not all mobile users; scope mismatch
   - Mobile platform is clear, but user cohort (new, returning, VIP) is not specified

---

## Improved Version

**If we send a push notification reminder 1 hour after cart abandonment to mobile users who have an active session history,
we expect abandoned cart recovery rate (orders placed within 7 days of notification) to increase by at least 8–12% relative to a no-notification control,
because timely reminders reduce user drop-off due to distraction and help users resume checkout intent.**

**Guardrails / Risk flags to monitor:**
- Push opt-out rate increase (users disabling notifications due to frequency)
- Order value or margin impact (recovered orders may be lower-value)
- Time-to-order latency (orders arriving much later may be lower confidence)

---

## Analysis Against Verdict Criteria

| Criterion | Status | Note |
|-----------|--------|------|
| One specific, isolated change | ✓ Yes | Push notification at 1-hour mark is a clear, single intervention |
| Target segment bounded and testable | ⚠ Partial | "All mobile users" is too broad; should narrow to "mobile users with abandoned carts" or refine by retention/value cohort |
| Primary metric clearly named and objectively measurable | ⚠ Partial | "Completed orders" is ambiguous (recovery vs. global count); recommend "abandoned cart recovery rate" |
| Plausible causal mechanism | ✓ Yes | Timely reminder reduces friction from distraction; mechanism is sound |
| Expected effect size defined | ✓ Yes | 25% uplift is stated explicitly |
| Effect size not wildly implausible | ✗ No | 25% uplift on order completion is implausibly high without prior evidence or contextual data. Cart recovery rates in published benchmarks are 5–15%, not 25% uplift on total orders |

---

## Why the Effect Size is a Red Flag

- **Push notification interventions for cart recovery** typically achieve 5–15% incremental recovery of abandoned carts, not 25% uplift on overall order completion
- **Context matters**: if the baseline recovery rate is 2%, a 25% *relative* uplift brings it to 2.5%—plausible. If the hypothesis means 25% *absolute* uplift, it is unrealistic
- **Single-touch interventions** are less effective than multi-touch sequences; a one-time notification at a fixed time is unlikely to move the needle by 25% without industry-specific context
- **Measurement risk**: if "completed orders" means the global order count, a push to cart abandoners cannot plausibly drive a 25% lift; that would require order inflation from entirely new users

---

## Missing Information

**Critical for upgrading to "Valid for experiment design":**
- Clarification: is 25% relative or absolute? Relative to what baseline?
- Historical or industry data on cart recovery rates for this product or segment
- Definition of "completed orders" — recovered from abandon, or total platform count?
- Segment refinement — why all mobile users, and not a cohort-specific test (new, returning, high-value, etc.)?
- Timing justification — why 1 hour? Is there data or hypothesis on optimal delay?

**Helpful but not blocking exploration:**
- Guardrail metrics (push opt-out rate, order value, time-to-order)
- Exclusion criteria (users who frequently disable notifications, high-frequency abandoners)
- Fallback or secondary outcomes if primary result is ambiguous

---

## Readiness Statement

**This hypothesis is NOT ready for experiment design.** It is valid for exploration — the intervention and causal logic are sound — but the 25% expected uplift is not justified by the context provided, and the primary metric definition is too ambiguous. Before designing a formal experiment, clarify the baseline, reframe the effect size with evidence or realistic benchmarking (suggest 8–12% relative recovery rate instead), narrow the segment or justify testing all mobile users, and define whether "completed orders" means recovered carts or global order count. Once these are resolved, hand off to define-success-metrics and design-experiment-plan.

---

## Next Steps

1. **Gather context:**
   - Pull historical cart recovery metrics for mobile cohort
   - Review any prior push notification or reminder experiments
   - Segment by user cohort (retention, order value, device type)

2. **Refine hypothesis:**
   - Replace 25% with realistic uplift target (e.g., "at least 8% relative recovery rate")
   - Specify the metric precisely (e.g., "cart recovery conversion rate within 7 days")
   - Justify timing (A/B test 1 hour vs. other delays, or use behavioral data)

3. **Design guardrails:**
   - Define success criteria (recovery rate threshold, notification opt-out tolerance)
   - Identify risk metrics (order value, margin, repeat purchase rate post-recovery)

4. **Return to validation:**
   - Resubmit refined hypothesis for "Valid for experiment design" verdict
   - Proceed to sample size estimation and experiment plan design
