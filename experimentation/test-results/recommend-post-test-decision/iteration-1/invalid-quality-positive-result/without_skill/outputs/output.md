# Post-Experiment Decision Recommendation

## Status
**DO NOT ROLLOUT — Rerun with proper experimental design**

## Summary
While the 7-day activation rate shows a strong numeric lift (+4.5pp, +14.4%), **the flexible stopping decision undermines the statistical validity of this result.** The team extended the experiment from 14 to 18 days because results weren't significant at the planned stopping point. This outcome-dependent decision inflates the false positive risk and makes the p-value unreliable, despite it appearing significant at p=0.001.

## Why This Matters
Flexible stopping is a classic violation of experimental integrity. When you peek at results and extend the experiment only because you didn't see significance, you're mining the data for a favorable result. The p-value threshold assumes a fixed stopping rule; violating that assumption breaks the statistical contract.

**The guardrail metrics (Day-30 retention, support tickets) are stable**, which is reassuring, but stability of secondary metrics doesn't remedy the primary quality issue. This is not a judgment about the primary metric itself — it's about whether we can trust the evidence.

## Next Steps
1. **Rerun the experiment** with a pre-committed stopping rule (14 days as originally planned, or a larger sample powered for 14 days)
2. **Do not implement based on this result alone** — the numeric pattern is interesting and worth exploring, but the decision process contaminated it
3. **Use this as sizing input**: The observed +4.5pp effect is useful for planning the rerun sample, but don't treat it as decision evidence

## Why Not Partial Rollout?
Partial rollout without addressing the quality issue just scales up an unvalidated change. If the effect disappears in the rerun, you've wasted implementation effort and user experience disruption.

## Detail: Understanding Flexible Stopping
The experiment was predefined for 14 days with 8,000 samples per group. At day 14, the result was not significant. The team then extended to 18 days to collect more data. This is the definition of outcome-dependent stopping: the decision to continue was based on whether the threshold had been crossed.

This practice inflates Type I error rates (false positives) because additional peeks and optional continuations increase the overall probability of seeing a significant result by chance. The p-value was calculated under the assumption of a fixed stopping rule, so its interpretation becomes unreliable.

## Guardrail Stability Does Not Override Quality Concern
- Day-30 retention: +0.3pp (p=0.61) — no statistical difference
- Support ticket rate: −0.2pp (p=0.44) — no statistical difference

These are genuinely stable and suggest the change doesn't harm downstream metrics. However, guardrail stability is a necessary but not sufficient condition. It does not validate the primary result when the experimental design itself is compromised.

## Recommendation
**Action**: Rerun
**Priority**: High (activation is a core KPI; the effect size if real would be meaningful)
**Timeline**: Plan for fixed 14-day window or pre-power a larger sample to reach significance within a committed timeframe
