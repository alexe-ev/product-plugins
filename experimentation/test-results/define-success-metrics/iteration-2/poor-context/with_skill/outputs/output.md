# A/B Test Success Metrics Definition

## Input Received
"Need metrics for an A/B test we're planning."

## Context Assessment
**Context level: Poor**

This request lacks critical details about the hypothesis, product goal, and funnel stage. No baseline metrics, known trade-offs, or risk context provided.

## What We Know
- An A/B test is planned
- Success metrics are needed
- No other details provided

## What Is Missing (Must Be Confirmed)
1. **What user outcome is meant to improve?** (activation, retention, conversion, revenue, engagement, etc.)
2. **Which funnel stage is affected?** (onboarding, free-to-paid, feature adoption, checkout, etc.)
3. **What is the business goal?** (grow users, increase revenue, improve retention, reduce churn, etc.)
4. **What is the actual hypothesis?** (what change are you testing and why?)
5. **What side effects are most risky?** (which metrics could worsen that would be problematic?)
6. **What level of improvement would matter?** (minimum meaningful effect)

## Recommended Metric Options (Provisional)

Since the intended outcome is unknown, here are the most common primary metric patterns by goal type:

### Option A: If the test affects user onboarding or first-time activation
**Primary Metric:** Activation rate (% of new users who complete initial onboarding or first key action)
**Secondary Metrics:**
- Time to activation
- Day 1 retention
**Guardrails:**
- Don't degrade user satisfaction
- Don't increase onboarding drop-off

### Option B: If the test affects purchase or checkout behavior
**Primary Metric:** Conversion rate (% of visitors who complete a purchase)
**Secondary Metrics:**
- Average order value
- Checkout completion rate
**Guardrails:**
- Revenue per visitor should not decrease
- Cart abandonment should not increase materially

### Option C: If the test affects ongoing engagement or habit
**Primary Metric:** Retention rate (% of users active in Day 7 or Day 30, depending on product cycle)
**Secondary Metrics:**
- Daily/weekly active users
- Session frequency
**Guardrails:**
- User satisfaction scores
- Churn rate should not increase

### Option D: If the test affects monetization (paying users)
**Primary Metric:** Revenue per user or annual recurring revenue per user
**Secondary Metrics:**
- Conversion to paid
- Lifetime value
**Guardrails:**
- Don't increase churn
- Free user engagement should not degrade

## What to Do Next

1. **Confirm the hypothesis:** What change is being tested and why?
2. **Clarify the business goal:** Which of the four outcomes above (activation, conversion, retention, revenue) best matches your test?
3. **Identify the funnel stage:** Where in your user journey does the tested change have its primary effect?
4. **Define risk tolerance:** Which metrics would be most damaging if they worsen?
5. **Set the minimum meaningful effect:** What % improvement would justify shipping the change?

Once you answer these questions, we can lock in the primary metric, define exact success thresholds, and prepare for sample size estimation.

## Output Structure (Ready for Downstream Use)

Once context is confirmed, output will include:
- ✓ Primary metric (currently: TBD)
- ✓ Secondary metrics (currently: TBD)
- ✓ Guardrail metrics (currently: TBD)
- ✓ Minimum meaningful effect (currently: TBD)
- ✓ Success threshold (currently: TBD)
- ✓ Neutral zone (currently: TBD)
- ✓ Failure threshold (currently: TBD)

## Provisional Status
**All metric choices are provisional** until the hypothesis, business goal, and funnel context are clarified.

---

**Next steps:** Share details about what you're testing and what outcome you're trying to improve, and we'll lock in the metric framework.
