# Hypothesis Validation: Push Notification for Cart Abandonment

## Input

**Hypothesis (original language):**
Если мы добавим push-уведомление с напоминанием о незавершённом заказе через 1 час после abandonment для всех мобильных пользователей, мы ожидаем рост завершённых заказов на 25%, потому что пользователи часто отвлекаются и забывают вернуться.

**Hypothesis (English translation):**
If we add a push notification reminder about an incomplete order 1 hour after abandonment for all mobile users, we expect a 25% increase in completed orders, because users often get distracted and forget to return.

---

## Verdict

**Valid for exploration** — the direction is promising and worth investigating, but the expected effect size of 25% is implausibly high without prior evidence or baseline context, and some measurement details need clarification.

---

## Main Weaknesses

1. **Implausible effect magnitude** — A 25% relative uplift in completed orders is a very large effect claim for a single intervention (push notification) on a mature product metric. This level of uplift typically requires:
   - Clear baseline data showing current cart abandonment recovery rates
   - Evidence that distraction/forgetfulness is the primary abandonment driver (vs. price, shipping cost, payment friction, etc.)
   - Prior similar tests showing effect of comparable magnitude
   - Without this, a 25% claim reads as aspirational rather than evidence-based

2. **Primary metric ambiguity** — "Completed orders" is the outcome, but the hypothesis does not specify:
   - Is this relative to all abandoned carts or only those who receive the notification?
   - Are you measuring recovery rate (abandoned → completed) or absolute order volume?
   - What counts as "completed" (payment confirmed, or order shipped)?
   - This ambiguity makes objective success evaluation harder

3. **Segment clarity** — "All mobile users" is bounded, which is good, but:
   - Does this include users who have disabled push notifications?
   - Are repeat abandoners treated the same as first-time abandoners?
   - Will the test exclude users who have already completed during the 1-hour window?
   - These details matter for segment stability in an experiment

4. **Causal mechanism is plausible but untested** — "Users often get distracted and forget" is a reasonable hypothesis, but:
   - No evidence is cited that distraction/forgetfulness is the dominant reason for abandonment
   - Other reasons (price sensitivity, payment issues, shipping delays) may be more common
   - The mechanism is intuitive but not validated against your actual user base

---

## Improved Version

If we send a push notification reminder 1 hour after cart abandonment to mobile users who have push notifications enabled, we expect the cart recovery rate (abandoned carts completed within 24 hours) to increase by at least 8%, because reminders can reduce friction when users have temporarily left the flow.

**Rationale for changes:**
- Lowered effect expectation from 25% to 8% (still meaningful but more conservative)
- Clarified the metric (cart recovery rate with a time window)
- Narrowed the segment (mobile + push-enabled)
- Specified the recovery window (24 hours post-abandonment)
- Softened the causal claim ("can reduce friction") rather than asserting distraction as the sole driver

---

## Missing Information

To upgrade this from "valid for exploration" to "valid for experiment design," provide:

1. **Baseline context:**
   - Current cart abandonment rate for mobile users
   - Current cart recovery rate (what % of abandoned carts are eventually completed?)
   - Breakdown of abandonment reasons (price/shipping concerns, payment friction, distraction, etc.)

2. **Effect size justification:**
   - Any prior push notification tests and their lift
   - Competitive or industry benchmarks for reminder notification effectiveness
   - A business rationale for the 25% target (vs. the more conservative 8% in the improved version)

3. **Measurement details:**
   - Definition of "completed order" (payment confirmed vs. order placed vs. order shipped)
   - Treatment of repeat abandoners (send notification only on first abandon? Each time?)
   - Holdout/control group definition and size

4. **Segment constraints:**
   - Will you exclude users with notifications disabled?
   - How will you handle the 1-hour delay (time zone handling, clock precision)?
   - Are there user cohorts (new vs. repeat, by device type, by traffic source) that should be analyzed separately?

---

## Readiness Statement

**This hypothesis is NOT ready for experiment design.** It requires evidence or justification for the 25% effect size claim, baseline cart recovery metrics, and clearer definitions of the primary metric (exact definition of "completed order" and the recovery window). Proceed with step 1: gather baseline context on mobile cart abandonment and recovery rates, and lower or defend the 25% expectation with prior test data.

---

## Notes for Next Steps

- **If you proceed to exploration:** Start by collecting 2–4 weeks of baseline data on mobile cart abandonment and recovery (current state). Segment by first-time vs. repeat abandoners to understand whether notification timing matters equally for both groups.
- **If you want to move to experiment design:** Reframe the hypothesis with a more conservative effect target (5–10% is more realistic for a single reminder intervention), and commit to a specific cart recovery definition upfront (e.g., "recovery rate = completed transactions from abandoned carts within 72 hours of abandonment").
- **Key guardrail to add:** Prepare a secondary metric (push notification opt-out rate, or uninstall rate) to ensure the reminder doesn't degrade user experience or app trust.
