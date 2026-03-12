# Experiment Analysis: Dashboard Redesign — Feature Engagement Score

## Primary Metric Comparison

**Feature Engagement Score (% of available features used per active day)**
- Control: 0.42
- Test: 0.46
- Absolute uplift: +0.04 (+4 percentage points)
- Relative uplift: +9.5%
- Sample size: 12,000 per group
- Duration: 2 weeks

## Statistical Summary

- **P-value: 0.004** — The observed difference is statistically significant at the 0.05 level. The probability of observing this effect by chance, assuming no true difference, is low.
- **95% Confidence Interval: [+1.4pp, +6.6pp]** — The true effect likely lies between a 1.4 and 6.6 percentage point uplift. This interval does not cross zero, supporting the statistical significance.
- **Sample sizes are adequate** (12,000 per group) for a 2-week test.

## Critical Temporal Pattern: Novelty Effect Concern

**Week-by-week breakdown:**
- Week 1: Control 0.41, Test 0.48 → **+7pp (+17% relative)**
- Week 2: Control 0.43, Test 0.44 → **+1pp (+2.3% relative)**

**This is a major red flag.** The effect decayed dramatically from Week 1 to Week 2:
- Week 1 showed a 17% relative uplift.
- Week 2 showed only a 2.3% relative uplift.
- This pattern is consistent with a **novelty effect** — users respond positively to the new, simpler interface initially, but the benefit erodes as they adapt.

**Week 2 statistical power:** The Week 2 uplift of +1pp (+2.3% relative) is likely **not statistically significant on its own**. The overall p-value of 0.004 is driven primarily by the Week 1 spike, not by stable, sustained improvement.

## Guardrail Summary

✓ Support tickets: within normal range
✓ Churn signal: within normal range
✓ NPS survey: within normal range

No negative side effects detected during the test window.

## Result Classification

**Positive with Caution** — NOT recommended to ship immediately.

Despite the overall statistical significance (p = 0.004), the rapid decay from Week 1 to Week 2 suggests the uplift may not persist post-launch.

## Practical Interpretation

1. **Short-term effect confirmed.** The redesigned dashboard did increase feature usage in the immediate post-launch window. However, this appears to be driven by novelty rather than sustained usability improvement.

2. **Steady-state effect unclear.** The Week 2 result (+1pp) may represent the true steady-state benefit, which is much smaller and possibly not practically meaningful. Alternatively, the effect could continue to decay further.

3. **Risk of rollback post-launch.** If you ship now and the effect continues to decay after launch, you may find that feature engagement returns to baseline, wasting engineering resources and creating confusion about product direction.

## Recommendations

**Option 1: Extend the test** (Preferred)
Run the test for at least one additional week (Week 3) to observe:
- Whether the effect stabilizes at the Week 2 level (+1pp)
- Whether it continues to decay toward zero
- Whether there is any sign of recovery (less likely)

**Option 2: Ship with post-launch monitoring** (If launch timeline is critical)
If you must ship before getting Week 3 data:
- Set a clear metric threshold for rollback (e.g., "if feature engagement drops below X% within 2 weeks post-launch, rollback")
- Monitor daily or weekly feature engagement in production
- Plan a quick rollback decision gate at the 2–3 week post-launch mark

## Key Caveats

1. **Novelty effects are common** in UI redesigns and are often indistinguishable from true improvements using short test windows.
2. **Two weeks may be too short** to characterize steady-state user behavior, especially for a feature adoption metric.
3. **Guardrails are clean**, which is good, but support tickets and churn lag engagement changes by days or weeks. Monitor these closely post-launch.
4. **The confidence interval is wide** ([+1.4pp, +6.6pp]), which means the true effect could still be meaningful — or could be at the lower bound, where it's less clear if it justifies the change operationally.

## Missing Context

- Is there historical data on novelty decay for similar redesigns at your company?
- What is the business value of a +1pp to +7pp engagement improvement? Is +1pp meaningful enough to justify the redesign cost and complexity?
- Are there leading indicators (e.g., user feedback, scroll depth, time-on-feature) that suggest the simplification is actually reducing friction, or is all the uplift novelty-driven?
