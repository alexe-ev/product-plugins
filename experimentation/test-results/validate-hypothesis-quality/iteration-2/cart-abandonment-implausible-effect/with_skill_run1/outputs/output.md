# Hypothesis Validation: Push Notification Reminder for Cart Abandonment

## Verdict
**Valid for exploration, but NOT ready for experiment design**

---

## Main Weaknesses

1. **Effect size is implausibly high without supporting data**
   - A 25% relative uplift on order completion is a very aggressive claim for a reminder notification alone
   - Mature e-commerce platforms typically see 5-15% recovery from abandonment reminders, and that includes email
   - Push notification alone (without email or other channels) would likely drive smaller gains
   - This effect claim lacks prior evidence or pilot data to justify the magnitude

2. **Multiple interventions mixed into one hypothesis**
   - The hypothesis bundles together: notification channel (push), timing (1 hour), content (reminder), and audience (all mobile users)
   - Testing "push notifications" as a monolith prevents isolating what actually drives conversion (is it the channel, the timing, the message, or the segment?)
   - For experiment design, each variable should be tested separately or the interaction should be explicitly justified

3. **Segment definition could be tighter**
   - "All mobile users" is broad and may mask important sub-segments
   - Mobile users vary by device, OS, notification permission status, engagement level
   - High-intent users may need different messaging than low-intent users
   - Users who have already received similar reminders may have notification fatigue

4. **Metric definition needs tightening**
   - "Completed orders" is clear, but what about order value?
   - Is this relative uplift or absolute?
   - Time window: completion within 24 hours? 7 days? Ever?
   - What about downstream metrics: AOV, return rate, customer satisfaction with push frequency?

5. **Timing assumption not tested**
   - The 1-hour delay is specified but not justified
   - Why 1 hour specifically? No evidence provided that this timing is optimal
   - Earlier or later notifications might perform differently

6. **Causal mechanism is incomplete**
   - The stated mechanism ("users get distracted and forget") is valid, but narrow
   - Real drivers might include: negative option bias, social proof in message, urgency signals, discount incentives
   - It's unclear whether the notification alone is doing the work or if it's the content/messaging

---

## Improved Version

**Instead of one broad hypothesis, split into:**

### Hypothesis A (Conservative, testable):
If we send a single push notification reminder 1 hour after cart abandonment to opted-in mobile users who have abandoned their first cart,
we expect the checkout completion rate (orders completed within 24 hours of abandonment) to increase by at least 8%,
because timely reminders reduce friction from context-switching and memory loss.

**Why this is better:**
- Narrows segment (first-time abandoners, opted-in users)
- Removes the 25% claim in favor of a more defensible 8%
- Specifies time window for conversion
- Isolates a single intervention (just the reminder, at a specific time)
- Mechanism is realistic given e-commerce benchmarks

### Hypothesis B (If effect size is truly expected to be 25%):
If we send a personalized push notification reminder 1 hour after cart abandonment with a limited-time discount code (15% off) to opted-in mobile users,
we expect the checkout completion rate to increase by at least 20%,
because combining timely reminders with incentive and scarcity signals will overcome abandonment friction and price sensitivity.

**Why this is better:**
- Explains the higher uplift through additional mechanisms (discount + scarcity, not just reminder)
- Still specifies the segment and time window
- Acknowledges that the 20%+ uplift likely requires more than notification alone
- Testable and defensible

---

## Missing Information for Experiment Design

To upgrade this to "Valid for experiment design," provide:

1. **Benchmark data**
   - What is the current cart abandonment recovery rate without any intervention?
   - What recovery rate have similar push notification campaigns achieved in your product?
   - Why is 25% the expected uplift, even after accounting for diminishing returns?

2. **Segment validation**
   - How many mobile users abandon carts per day?
   - What percentage have push notifications enabled?
   - Is there evidence that this segment actually has high "forgetting" behavior vs. decision resistance?

3. **Notification permission strategy**
   - How will you handle users who don't have push enabled?
   - Will you fall back to email, or exclude them?
   - Does this change the expected effect?

4. **Guardrail metrics**
   - Will you monitor notification opt-out rate?
   - Will you check for downstream effects on customer lifetime value or repeat purchase rate?
   - Are there scenarios where this drives completion but hurts long-term loyalty?

5. **Causal isolation**
   - If you truly believe the effect is 25%, what components of the notification are driving it?
   - Is it the push channel itself, the timing, the message content, or a combination?
   - Should you test a simpler version first (e.g., notification with no message changes)?

---

## Readiness Statement

**This hypothesis is NOT ready for experiment design.** It requires downward revision of the expected effect size from 25% to a defensible 8-15% range (with supporting evidence), tighter segment definition, isolation of the intervention, and clarification of whether additional levers (e.g., discount codes) are part of the treatment. It is ready for exploration if the team wants to pilot a conservative version (e.g., 8% uplift expectation) and validate whether the causal mechanism holds at all before running a full experiment.

---

## Context Classification

**Context level: Light**
- Clear product area (checkout/cart abandonment recovery)
- Clear metric (order completion)
- Clear target segment (mobile users)
- Clear intervention (push notification at 1 hour)
- **Gap:** Effect size claim is unsupported and implausibly high; intervention may conflate multiple levers
