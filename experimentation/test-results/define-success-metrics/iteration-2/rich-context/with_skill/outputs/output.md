# Success Metrics Framework: Weekly Spending Summary Experiment

## Input Summary
**Hypothesis:** If we show users a weekly spending summary inside the app, more users will stay active past day 30 — because they'll have a reason to return and check their progress.

**Business goal:** Improve 30-day retention without increasing notification opt-outs or creating anxiety around spending habits.

---

## Primary Metric

**Metric:** 30-day retention rate
- Definition: % of users active (at least one app session) on or after day 30 from their install date
- Measurement: Tracked at the cohort level over 30+ days post-install

**Why it is primary:**
- The hypothesis explicitly targets improving retention past day 30
- It is the closest measurable outcome to the stated goal
- It reflects the core user engagement outcome the feature is designed to drive
- It is a leading indicator of product health and sticky behavior

---

## Secondary Metrics

1. **Weekly engagement rate (days 21-30)**
   - % of users active in at least 3 out of 4 weeks post-install
   - Diagnostic: Shows whether users are establishing a weekly check-in habit

2. **Session frequency in week 4**
   - Average sessions per active user in days 22-30
   - Diagnostic: Indicates repeat visitation and habit strength

3. **Day 7 and Day 14 retention**
   - Milestone checks earlier in the funnel
   - Diagnostic: Confirms the retention effect emerges and compounds over time

4. **Feature adoption rate**
   - % of users who view the weekly spending summary at least once
   - Diagnostic: Baseline for feature usage; validates the feature reaches users

5. **Summary engagement depth**
   - Average time spent viewing the summary; repeat views per week
   - Diagnostic: Shows whether the feature creates enough value to drive repeat visits

---

## Guardrail Metrics

1. **Notification opt-out rate**
   - % of users who disable push notifications during the experiment window
   - Risk: The feature or its notification strategy could create fatigue or anxiety
   - Success: No material increase vs. control

2. **Support contacts related to spending/budget anxiety**
   - Volume of support tickets mentioning anxiety, stress, or budget-related concerns
   - Risk: Exposure to spending data could trigger unintended psychological responses
   - Success: No material increase vs. control

3. **App uninstall/churn rate (days 7-30)**
   - % of users who delete or stop using the app during the experiment window
   - Risk: If the spending summary triggers negative emotions, churn could increase
   - Success: No material increase vs. control

4. **Day 1 retention**
   - % of users active on day 1 post-install
   - Risk: Changes to the app experience could disrupt early onboarding
   - Success: No material degradation vs. control

5. **Error rate during summary view**
   - % of summary views that result in a loading error or crash
   - Risk: A new feature could introduce technical debt or instability
   - Success: Error rate below 2%

---

## Success / Neutral / Failure Thresholds

**Minimum meaningful effect:**
- 30-day retention rate improvement of **2–3 percentage points** (relative +3–5% improvement)
- Rationale: Retention gains at this scale are operationally meaningful for user lifetime value and churn reduction. Below 2 pp is likely noise; above 3 pp is a strong signal.
- **Note:** This should be confirmed with the product and business team based on target cohort size and business impact.

**Success threshold:**
- Primary metric (30-day retention) improves by ≥2 percentage points (relative +3%+)
- **AND** all guardrails show no material degradation (≤1% adverse change)
- Recommended interpretation: Roll out the feature

**Neutral zone:**
- Primary metric shows 0–2 percentage point improvement
- All guardrails are stable
- Interpretation: Modest or inconclusive result; gather more data, iterate on the feature, or consider other drivers of retention

**Failure threshold:**
- Primary metric shows no improvement or declines
- **OR** any guardrail metric materially worsens (>1% adverse change, especially opt-outs or churn)
- Interpretation: Do not roll out; investigate why retention did not improve and revisit the feature design

---

## Minimum Meaningful Effect

**30-day retention improvement: 2–3 percentage points**

**Rationale:**
- Current baseline 30-day retention is typically 25–45% for consumer apps (varies by category)
- A 2 pp improvement represents meaningful impact on lifetime value and user acquisition payback
- Requires a sufficiently large sample size to detect; typically 2,000–5,000+ users per arm
- Should be confirmed with the product and analytics teams before sample size estimation

---

## Interpretation Notes

1. **Retention is the right primary metric** because the hypothesis explicitly targets day 30+ engagement and the business goal mentions retention improvement.

2. **Weekly engagement is a strong diagnostic** because it hints at whether the summary is creating a recurring habit (the mechanism proposed in the hypothesis) or just a one-time lift.

3. **Guardrails are essential** because the business goal explicitly mentions two risks:
   - Notification opt-out increases (anxiety or fatigue from the feature)
   - Increased anxiety around spending (psychological harm risk)
   - The guardrails directly address these concerns

4. **Feature adoption should be measured** to confirm the summary is actually being seen. If adoption is very low (<20%), retention improvements may be driven by other factors.

5. **Day 7 and Day 14 retention** should be tracked to confirm the effect emerges early and compounds over time, rather than being a spurious week-4 spike.

---

## Provisional Context

**Aspects locked:**
- Primary metric (30-day retention)
- Core secondary and guardrail metrics
- High-level success/failure logic

**Aspects requiring confirmation before final sample size estimation:**
- Minimum meaningful effect size (2–3 pp) should be reviewed by product and business stakeholders
- Guardrail thresholds (1% degradation) should be reviewed by the trust and safety or support team
- Baseline 30-day retention rate and expected variance (needed for power calculation)
- Notification opt-out behavior and typical risk thresholds in the product
- Support contact volume and typical weekly variance for anxiety-related tickets

---

## Downstream Handoff Readiness

This framework is ready to hand off to:
- **estimate-sample-size:** Primary metric (30-day retention), minimum effect (2–3 pp), baseline rate, and planned arms are defined
- **design-experiment-plan:** Metric definitions, success criteria, and guardrail thresholds are clear
- **result analysis:** All metrics are defined operationally; interpretation rules are set

**Before proceeding to sample size estimation, confirm:**
1. Minimum meaningful effect (2–3 pp) aligns with business priorities
2. Baseline 30-day retention and its variance for the target cohort
3. Guardrail thresholds are acceptable to the product and support teams
