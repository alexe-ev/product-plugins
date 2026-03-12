## Recommended action
**Rerun the experiment with a pre-specified stopping rule**

## Why this action is appropriate

The experiment shows a strong numeric result (4.5pp lift, p=0.001), and guardrails are stable. However, the **quality audit reveals flexible stopping**: the team extended the test from 14 to 18 days because results weren't significant at the planned endpoint, then stopped once significance was achieved. This is outcome-dependent stopping, which inflates the false-positive rate and undermines the reliability of the reported p-value.

The p-value of 0.001 cannot be trusted for decision-making in its current form. A p-value computed after peeking and extending based on intermediate results does not carry its nominal interpretation. Even a very small p-value becomes unreliable when the stopping rule depends on the observed data.

The numeric result itself (4.5pp activation lift) is meaningful and suggests a real effect is plausible. But the current evidence is insufficient to justify rollout.

## Risks

- **Rollout based on this result risks adopting a false positive**: If the true effect is smaller (or null), rollout commits resources and reputation to a design change with no real benefit.
- **Delayed impact**: Rerunning costs time. If the effect is real, implementation is delayed.
- **Team disappointment**: The team invested in this change and saw a "strong" result; rerunning may feel conservative.

## What should happen next

1. **Rerun the experiment** with:
   - Pre-specified sample size (based on the observed 4.5pp effect size for power calculation)
   - Pre-specified stopping rule (e.g., fixed sample size with no peeking, or Bayesian sequential design with pre-committed boundaries)
   - Same primary and guardrail metrics

2. **Use the current result to inform the rerun size**: The observed 4.5pp lift is useful for sample size estimation. A rerun powered to detect this effect size (or a smaller, realistic effect) will resolve the ambiguity.

3. **If the rerun confirms the effect**, rollout becomes justified.

4. **If the rerun shows a smaller or null effect**, the change should be rejected or iterated further.

## Which missing business inputs limit recommendation strength

None critical—the quality issue is sufficient to override the rollout case regardless of cost or strategic priority.
