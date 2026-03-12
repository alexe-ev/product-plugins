# Experiment Analysis: Mobile Game Tutorial Difficulty

## Recommendation: DO NOT SHIP — Hold for further investigation

---

## Primary Metric Analysis

Your experiment shows a clear positive impact on tutorial completion:

- **Day-1 Tutorial Completion:** 62.0% → 68.0% (+6.0pp absolute, +9.7% relative)
- **Statistical Confidence:** With p=0.001 and a 95% CI of +3.8pp to +8.2pp, this result is highly statistically significant and the true effect is unlikely to be below 3.8pp improvement.
- **Sample Size:** 15,000 per group is robust.

This is a genuine win on the primary metric.

---

## Critical Guardrail Issue

However, the Day-7 retention rate tells a concerning story:

- **Retention Degradation:** 28.0% → 24.0% (−4.0pp absolute, −14.3% relative decline)

This is not a minor fluctuation — it represents a 14% relative decline in week-1 retention. This suggests that while the reduced tutorial difficulty successfully gets more players through the tutorial, those players may have lower quality or lower intent. The easier tutorial appears to be attracting or enabling less-engaged cohorts who don't return.

---

## The Trade-off

You've optimized for funnel velocity (tutorial completion) at the expense of engagement quality (retention). Easier tutorials can sometimes create a false sense of progression for low-intent users who have no intention of playing beyond the first day. They complete the tutorial, get immediate positive reinforcement, but don't match your game's actual difficulty or intended experience.

---

## Why Not Ship

- A 6pp improvement in tutorial completion paired with a 4pp drop in Day-7 retention suggests this change is **not beneficial to long-term growth**. Retention is typically more predictive of LTV than early-stage funnel metrics.
- The guardrail was violated materially — the margin of concern (4pp) is two-thirds the size of the primary metric win (6pp).

---

## What to Do Next

1. **Investigate the cohort:** Do players who complete the easier tutorial progress differently in later levels? Are they churning at specific difficulty spikes post-tutorial?
2. **Segment the retention:** Does the retention drop affect all user types equally, or only certain cohorts (e.g., casual vs. hardcore players)?
3. **Consider a middle ground:** Instead of wholesale difficulty reduction, test a more surgical change — e.g., better onboarding/explanation without full difficulty reduction.
4. **Measure engagement quality:** Look at Day-1 session length, progression speed, or secondary actions to understand whether tutored users are shallower engagers.

---

## Status

Positive primary metric + material guardrail conflict = **Not ready to ship.**
