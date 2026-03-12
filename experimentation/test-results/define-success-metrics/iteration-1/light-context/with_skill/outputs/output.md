# Success Metrics Framework
## Experiment: Simplify Sign-up to Increase Activation

---

## Primary Metric

**Metric Name:** Activation Rate (within 7 days of sign-up)

**Definition:** Percentage of users who complete the sign-up flow and reach the activation milestone within 7 days of account creation.

**Why it is primary:**
- The hypothesis explicitly targets activation as the outcome
- Activation is the named business goal in the hypothesis
- It is the closest measurable outcome to the sign-up simplification change
- Directly reflects whether the change achieves its intended purpose
- Time-bounded to 7 days to capture immediate impact of sign-up friction reduction

---

## Secondary Metrics

**Sign-up Completion Rate**
- Percentage of users who start the sign-up flow and complete all required steps
- Diagnostic indicator of whether simplification reduced drop-off during registration
- Helps identify if changes shifted friction to a different stage

**Time to Activation**
- Median and 90th percentile time from sign-up completion to activation
- Reveals whether simplification not only increases activation but accelerates it
- Supports efficiency measurement alongside outcome improvement

**Drop-off by Registration Step**
- Completion rate at each step of the simplified sign-up flow
- Identifies if new design eliminates specific friction points or creates new ones
- Enables iteration on remaining bottlenecks

**Sign-up Error Rate**
- Percentage of sign-up attempts that encounter validation or system errors
- Ensures simplification didn't introduce technical or UX bugs

---

## Guardrail Metrics

**Early Retention (Day 1 and Day 7)**
- Percentage of activated users who return on Day 1 and Day 7
- Ensures that accelerated activation doesn't mean onboarding low-quality users
- Catches if simplified sign-up trades quality for quantity

**Support Contacts Related to Registration**
- Count of support tickets, chat, or help requests about sign-up or account creation
- Indicates if simplification created confusion or unmet user needs
- Should not increase materially

**Account Validation / Data Quality Issues**
- Percentage of accounts flagged for suspicious, duplicate, or incomplete data
- Guards against lowered barriers enabling spam, fraud, or low-intent signups
- Should remain stable or improve

---

## Thresholds and Decision Criteria

**Minimum Meaningful Effect:**
[PROVISIONAL - Requires team confirmation]

Suggest: ≥5% relative improvement in activation rate
- Rationale: Modest but meaningful change that justifies friction reduction without overshooting user experience requirements
- Must be calibrated based on implementation cost, business opportunity, and baseline activation rate

**Success Threshold:**
- Primary metric (activation rate) improves by **at least the agreed minimum meaningful effect** (e.g., ≥5% relative uplift)
- **AND** no material guardrail degradation:
  - Early retention stable or improved
  - Support contacts do not increase significantly
  - Data quality issues do not increase materially
  - Sign-up error rate stable or improved

**Neutral Zone:**
- Activation rate improvement falls between 0% and the minimum meaningful effect threshold
- Suggests change may have marginal value but insufficient return to justify rollout
- Consider secondary metric performance before deciding

**Failure Threshold:**
- Activation rate shows no improvement or declines
- **OR** guardrails degrade meaningfully:
  - Day 1/Day 7 retention drops >2% relative
  - Support contacts increase by >20% relative
  - Data quality issues increase >10% relative
  - Sign-up error rate increases significantly

---

## Interpretation Notes

**Confidence Level:** Light-context framework
- Activation metric is well-aligned with hypothesis
- Exact activation definition and time window should be confirmed (7 days is provisional)
- Team must align on what constitutes "meaningful" improvement before locking sample size

**Key Assumptions:**
- "Activation" is a well-defined binary or rate metric in your product (e.g., completing onboarding, taking first action, reaching core feature)
- Sign-up is a distinct conversion funnel step before activation
- Users who complete sign-up can fail to activate
- 7-day window captures the expected impact window

**Risks to Monitor:**
- Selection bias: simpler sign-up may attract different user cohorts with different retention profiles
- Quality vs. quantity tradeoff: simplification may lower intent or information quality of signups
- False activation: more users completing nominal activation without genuine value realization

---

## What is Provisional Due to Missing Context

**Must Confirm Before Finalizing:**
- [ ] Exact definition of "activation" in your product (specific action, milestone, or behavior)
- [ ] Time window for activation measurement (7 days suggested, could be 1, 14, or 30 depending on product)
- [ ] Minimum meaningful effect size (suggested 5% relative, must align with business goals and implementation ROI)
- [ ] Baseline activation rate (needed to calculate absolute vs. relative improvement)
- [ ] Definition of guardrail thresholds (suggested ranges provided above, must be calibrated to risk tolerance)
- [ ] Segment-specific considerations (does success metric differ by device, geography, user source, etc.?)

---

## Readiness for Downstream Work

**Ready for:**
- Sample size estimation (once minimum meaningful effect is confirmed)
- Experiment plan design
- Baseline metric validation

**Not yet ready for:**
- Final sample size calculation
- Experiment launch
- Success/failure determination

**Next Steps:**
1. Team agrees on activation definition and time window
2. Confirm minimum meaningful effect threshold with stakeholders
3. Validate baseline metrics and guardrail baselines
4. Proceed to sample size estimation with confirmed parameters
