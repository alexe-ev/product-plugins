## Experiment Readout: Push Notification Strategy A/B Test

### Primary Metric: Notification Open Rate

**Observed Effect:**
- Control: 18.3% (45,000 notifications)
- Test: 24.1% (82,000 notifications)
- Absolute uplift: +5.8 percentage points
- Relative uplift: +31.7%
- 95% CI: +4.1pp to +7.5pp

The test variant shows a statistically significant improvement (p = 0.001), with a confidence interval that does not cross zero, providing strong evidence that the true uplift lies between +4.1pp and +7.5pp.

### Critical Confound: Notification Volume Imbalance

**Important caveat:** The test group received 82,000 notifications versus 45,000 in the control—an 82% increase in volume. This creates a fundamental confound that undermines the open rate comparison.

The higher open rate in the test group cannot be cleanly attributed to the "smart send" algorithm's quality. Part or all of the uplift may reflect:
- Selection effects (more engaged users receiving more notifications)
- Recency/frequency effects (more notifications = more opportunities to open)
- Novelty bias (algorithm-selected messages may feel fresh)

**We cannot determine how much of the +5.8pp uplift reflects genuine algorithm quality versus the volume differential.**

### Guardrail: Notification Opt-Out Rate — CRITICAL FAILURE

- Control: 2.1%
- Test: 4.8%
- Change: +2.7 percentage points (opt-outs more than doubled)

This is a severe guardrail breach. Users in the test group are opting out at more than double the rate. This signals:
- User dissatisfaction with the test experience
- Potential for sustained user churn if shipped
- No statistical significance provided for this metric, but the magnitude is large enough to be practically concerning

**The opt-out increase is not a minor trade-off—it directly contradicts the premise that the algorithm improves user satisfaction.**

### Result Classification: **Negative — Do Not Ship**

**Rationale:**
1. The primary metric improvement cannot be trusted due to confounding volume differences.
2. The guardrail metric (opt-out rate) shows clear user rejection, more than doubling in the test group.
3. Even if the open rate uplift were genuine, shipping a change that doubles user opt-outs is not a net positive outcome.

**The test provides evidence of a failed variant, not a successful one.**

### Key Caveats

- The open rate delta may be partially or entirely explained by higher notification volume in the test group, not algorithm quality.
- The opt-out rate increase is the strongest signal in this test and should override the primary metric result.
- To properly evaluate the "smart send" algorithm, a future test would need to hold notification volume constant between control and test while varying the selection strategy.

### Missing Context

- How many users are in each group (sample size for statistical power assessment)?
- Why was notification volume allowed to differ between variants? Was this intentional or a procedural issue?
- What is the business threshold for acceptable opt-out rates?
- Are there any segment-level patterns (e.g., does the guardrail failure occur across all user types)?
