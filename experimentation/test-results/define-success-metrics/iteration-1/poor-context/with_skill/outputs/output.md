# Success Metrics Framework for Experiment

## Executive Summary
The request for success metrics lacks critical context required to define a single "correct" metric framework. This document provides **conditional metric options** based on different possible experiment goals, alongside a checklist of what must be confirmed before sample size estimation and experiment planning can proceed.

---

## Critical Missing Context

Before any metrics can be finalized, the following must be confirmed:

### 1. **What user outcome is the change meant to improve?**
   - Activation (getting started/first value)
   - Conversion (purchase/transaction completion)
   - Retention (returning/repeated usage)
   - Revenue (monetization/ARPU)
   - Engagement (time spent, feature adoption)
   - Other: _______________

### 2. **At what funnel stage should the effect appear?**
   - Awareness/Discovery
   - Onboarding/Sign-up
   - First use/Value realization
   - Sustained usage
   - Purchase/Monetization
   - Post-purchase/Retention

### 3. **What is the product context?**
   - Is this a consumer or B2B product?
   - Is the product new, growth-stage, or mature?
   - What is the current user base size?
   - What is the primary revenue model (if any)?

### 4. **What side effects are most risky in this product?**
   - User experience degradation
   - Support burden increase
   - Retention drop-off
   - Revenue cannibalization
   - Data quality issues
   - Other: _______________

### 5. **What is the risk tolerance for this experiment?**
   - Conservative (high confidence required before rollout)
   - Moderate (reasonable confidence acceptable)
   - Aggressive (learning/exploration mode)

---

## Conditional Metric Frameworks

Depending on the confirmed goal, choose the appropriate framework below:

### **OPTION A: If the Goal is User Activation**

#### Primary Metric:
**Activation rate within [7/14/30 days] of sign-up**

Why it is primary:
- Directly measures whether users achieve first value
- Aligned with user onboarding hypothesis
- Early-stage indicator of product-market fit

#### Secondary Metrics:
- Time-to-activation (speed measure)
- Sign-up completion rate (funnel health)
- Drop-off by onboarding step (diagnostic)
- Cohort-specific activation (by user segment/device)

#### Guardrail Metrics:
- Sign-up error rate
- Support contacts related to onboarding
- Day 1 retention (ensure quality activation)
- Data integrity issues during sign-up

#### Minimum Meaningful Effect:
**MUST BE DEFINED** — Example thresholds:
- 2-5 percentage point absolute improvement in activation (typical for mature products)
- 10-15% relative improvement in activation (realistic for early-stage products)
- Business decision: What improvement justifies engineering effort and rollout risk?

#### Success Criteria:
- Primary metric improves by **[X]%** or more, AND
- Guardrails show no material degradation (< 5% relative decline)

#### Neutral Zone:
- Improvement between 0% and [X]% (less than meaningful effect)
- Guardrails stable within ±5%

#### Failure Criteria:
- No improvement in primary metric, OR
- Any guardrail metric declines by > 5-10% relative

---

### **OPTION B: If the Goal is Purchase/Conversion**

#### Primary Metric:
**Conversion rate from [entry point] to purchase**

Why it is primary:
- Directly tied to revenue impact
- Clear, measurable outcome
- Standard business metric

#### Secondary Metrics:
- Cart completion rate
- Checkout error rate
- Time-to-purchase
- Average order value
- Repeat purchase rate (if applicable)

#### Guardrail Metrics:
- Return/refund rate
- Support contacts related to purchases
- User satisfaction (NPS, CSAT if available)
- Data quality during checkout

#### Minimum Meaningful Effect:
**MUST BE DEFINED** — Example thresholds:
- 1-3 percentage point absolute improvement (typical for commerce)
- 5-10% relative improvement
- Revenue impact calculation needed

#### Success Criteria:
- Primary metric improves by **[X]%** or more, AND
- Revenue impact justifies implementation cost, AND
- Guardrails remain stable

#### Neutral Zone:
- Improvement below meaningful threshold
- Guardrails stable

#### Failure Criteria:
- No improvement or decline in conversion
- Increased refund rate or support burden
- Revenue per user declines

---

### **OPTION C: If the Goal is Retention/Engagement**

#### Primary Metric:
**[Day 7 / Day 30 / 3-month] retention rate**

Why it is primary:
- Measures sustained product value
- Leading indicator of revenue potential
- Indicates product-market fit strength

#### Secondary Metrics:
- Day N retention (multiple timeframes)
- Session frequency
- Feature adoption rate
- Time spent in product
- Churn rate

#### Guardrail Metrics:
- Day 1 retention (quality of new acquisition)
- Support contacts or error rates
- User satisfaction
- Data completeness

#### Minimum Meaningful Effect:
**MUST BE DEFINED** — Example thresholds:
- 3-5 percentage point improvement in day 7 retention
- 5-10% relative improvement
- Cohort lifetime value impact

#### Success Criteria:
- Primary metric improves by **[X]%** or more, AND
- Effect persists across multiple cohorts, AND
- Guardrails stable

#### Neutral Zone:
- Improvement below threshold
- Guardrails stable

#### Failure Criteria:
- No improvement in retention
- Degradation in early-day retention (users leaving faster)
- Increased support burden

---

### **OPTION D: If the Goal is Revenue/Monetization**

#### Primary Metric:
**Revenue per user (RPU) or Average revenue per user (ARPU)**

Why it is primary:
- Direct business impact
- Aggregates conversion, frequency, and value
- Ultimate success metric

#### Secondary Metrics:
- Conversion rate
- Average order value / revenue per transaction
- Purchase frequency
- Customer lifetime value (if available)
- Subscription retention (if applicable)

#### Guardrail Metrics:
- User satisfaction / churn
- Support costs
- Refund rate
- Data quality issues

#### Minimum Meaningful Effect:
**MUST BE DEFINED** — Example thresholds:
- 2-5% improvement in RPU (business viability threshold)
- Confidence level: 90% or higher
- Expected sample size implications

#### Success Criteria:
- Primary metric improves by **[X]%** with acceptable confidence level (90%+), AND
- Business case justifies rollout, AND
- Guardrails stable

#### Neutral Zone:
- Improvement below business threshold
- Guardrails stable

#### Failure Criteria:
- No improvement or revenue decline
- Increased churn or support burden
- Negative impact on user experience

---

## General Guardrail Principles

Regardless of primary metric choice, consider guardrails for:
- **User experience:** Error rates, data loss, session stability
- **Business health:** Refund rate, support burden, compliance violations
- **Data quality:** Missing values, tracking errors, bot activity
- **User retention:** Ensure the change doesn't harm longer-term retention
- **Segment-specific effects:** Test if guardrails hold across critical user segments

---

## Before Sample Size Estimation Can Proceed

**Lock the following:**

1. ✓ Primary metric choice (must align with stated goal)
2. ✓ Minimum meaningful effect (as absolute and relative improvement)
3. ✓ Statistical confidence target (typically 90% minimum)
4. ✓ Guardrail thresholds (maximum acceptable degradation)
5. ✓ Success/failure decision rules
6. ✓ Duration estimate (when will metric stabilize?)
7. ✓ Relevant segments (test all users or specific cohorts?)

---

## Recommended Next Steps

1. **Confirm the primary goal** from the options above
2. **Define hypothesis specificity:** The more specific the hypothesis, the better the metric choice
3. **Quantify minimum meaningful effect** with product leadership and data science
4. **Identify key guardrails** for your product's unique risks
5. **Document assumptions** about user behavior, baseline metrics, and statistical power
6. **Hand off to sample-size estimation** using the locked framework

---

## Interpretation Notes

- This framework is **entirely provisional** due to missing context
- All metric choices above are **conditional** — select only the option that matches your actual goal
- If the actual goal differs from these options, iterate on the framework with the confirmed goal
- The skill downstream (sample-size estimation) will fail or produce unusable results if these details remain undefined

---

## Provisional Status Summary

| Component | Status |
|-----------|--------|
| Primary metric | **Provisional** — 4 options provided |
| Secondary metrics | **Provisional** — tied to primary choice |
| Guardrail metrics | **Provisional** — generic list provided |
| Minimum meaningful effect | **MISSING** — must be defined |
| Success threshold | **MISSING** — depends on primary metric and business context |
| Neutral zone | **Provisional** — awaiting meaningful effect definition |
| Failure threshold | **Provisional** — depends on guardrail choices |
| Risk tolerance | **UNKNOWN** — must be confirmed |
| Product context | **UNKNOWN** — must be provided |

---

## Not Ready For

- Sample size estimation (requires locked primary metric and meaningful effect)
- Experiment design planning (requires all thresholds defined)
- Result interpretation (requires guardrail definitions)

## Ready For

- Discussion with product leadership on goal alignment
- Selecting the appropriate metric framework
- Confirming critical context
