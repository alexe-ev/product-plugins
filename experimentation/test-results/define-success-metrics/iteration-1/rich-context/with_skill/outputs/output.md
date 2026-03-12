# Success Metrics Framework: Onboarding Reduction (5 → 3 steps)

## Experiment Summary
**Hypothesis:** If we reduce onboarding from 5 steps to 3 for new iOS users, we expect more users to start their first lesson.

**Business Goal:** Increase new-user activation without hurting Day 1 retention.

**Audience:** New iOS users

---

## Primary Metric

**Metric:** First-session lesson start rate

**Definition:** Percentage of new iOS users who initiate their first lesson within their first session (session window: first 24 hours post-signup).

**Why it is primary:**
- It directly measures the outcome named in the hypothesis: "more users to start their first lesson"
- It is the closest measurable proxy for activation and first value realization
- It appears at the funnel stage most likely to be affected by onboarding friction reduction
- Success here indicates the hypothesis is validated

---

## Secondary Metrics

These metrics provide diagnostic power and help interpret the primary metric result:

1. **Onboarding completion rate**
   - Definition: Percentage of new iOS users who complete all onboarding steps (whether 5 or 3 depending on variant)
   - Why it matters: Validates that the reduced-step variant is actually more completable; if this doesn't improve, the hypothesis may not be testable

2. **Time to first lesson (seconds/minutes)**
   - Definition: Median and mean time from signup to first lesson start, measured in new iOS users' first session
   - Why it matters: Directly measures friction reduction; should show clear improvement if the change works as intended

3. **Drop-off by onboarding step**
   - Definition: Breakdown of drop-off rate at each step of the onboarding flow (Step 1, 2, 3 in treatment; Step 1–5 in control)
   - Why it matters: Diagnostic signal showing where users leave; reveals if removed steps were actually high-friction bottlenecks

4. **Post-onboarding lesson engagement rate**
   - Definition: Among users who complete onboarding, percentage who then start a lesson
   - Why it matters: Isolates the effect of onboarding friction from downstream content appeal; if high, onboarding was the barrier

---

## Guardrail Metrics

These metrics should not worsen materially to consider the experiment a success:

1. **Day 1 retention**
   - Definition: Percentage of new iOS users who return the app on Day 1 (within 24 hours of signup)
   - Why it matters: Explicitly named in the business goal; guardrail against trading activation for immediate churn

2. **Onboarding error or crash rate**
   - Definition: Percentage of new iOS users who encounter technical errors, crashes, or get stuck during onboarding
   - Why it matters: Removing steps might skip validation logic; we must ensure quality doesn't regress

3. **Support contacts related to onboarding/signup**
   - Definition: Number of support tickets or in-app help requests per 1,000 new iOS users mentioning onboarding, signup confusion, or missing features
   - Why it matters: If removed steps cause confusion, support load may spike; this signal indicates downstream friction we can't see in funnel metrics

4. **Day 7 retention**
   - Definition: Percentage of new iOS users who return the app by Day 7
   - Why it matters: Ensures the cohort remains healthy beyond Day 1; catching earlier if reduced onboarding trades long-term engagement for short-term activation

---

## Minimum Meaningful Effect

**For primary metric (First-session lesson start rate):**
- Provisional baseline: assume ~30–40% of control users start a lesson in first session (to be confirmed from actual data)
- Minimum meaningful effect: **3–5 percentage point absolute uplift** (i.e., control at 35% → treatment at 38–40%)
- Rationale: Small absolute uplift in a high-intent group (new signups) typically represents strong product-market signal; exact threshold should be calibrated with product and business stakeholders based on:
  - Expected implementation cost
  - Revenue impact per additional activated user
  - Competitive urgency

---

## Success Thresholds

| Outcome | Condition |
|---------|-----------|
| **Success** | Primary metric improves by at least the minimum meaningful effect (3–5 pp) AND all guardrail metrics remain flat or improve (no material degradation) |
| **Probable Success** | Primary metric shows >1 pp improvement with favorable secondary diagnostics (reduced time-to-lesson, lower drop-off at removed steps) AND guardrails hold |
| **Neutral** | Primary metric shows <1 pp movement OR primary moves +2–3 pp but guardrails show slight degradation that is acceptable (e.g., <0.5 pp Day 1 retention drop) |
| **Failure** | No meaningful primary metric uplift (<1 pp) OR material guardrail damage (e.g., >1 pp Day 1 retention drop, support tickets spike >20%) |

---

## Interpretation Notes

1. **Primary metric is strong because:**
   - The hypothesis explicitly names lesson start as the outcome
   - Onboarding friction is a known funnel stage that can affect activation
   - First-session lesson start is a clear, measurable milestone

2. **Guardrail strategy is defensive:**
   - Day 1 retention is called out in the business goal; it is non-negotiable
   - Support and error metrics catch hidden friction from removed steps
   - Day 7 retention backstops concern about "activation without durability"

3. **Secondary metrics provide diagnostic power:**
   - If primary improves but onboarding completion doesn't, the 3-step variant may not be tested properly
   - If time-to-lesson doesn't drop, friction reduction wasn't the lever
   - Drop-off by step identifies which removed steps actually mattered

4. **Segments and context:**
   - This framework is specific to new iOS users (as per hypothesis)
   - Consider testing Android separately if roadmap allows; results may differ due to OS-specific onboarding patterns
   - If cohort is very small (<10k users per week), sample size constraints may require longer experiment windows

---

## What Is Provisional (Due to Missing Context)

1. **Minimum meaningful effect:** Recommended 3–5 pp, but must be confirmed with product/business based on:
   - Historical baseline for first-session lesson start in this iOS cohort
   - Expected magnitude of friction reduction from 5→3 steps
   - Business tolerance for experiment duration and false positive risk

2. **Success threshold for guardrails:** Flagged as "material degradation" but specific acceptable thresholds (e.g., max tolerable Day 1 retention drop) should be locked with stakeholders before experiment launch

3. **Experiment duration:** Not specified; depends on:
   - Daily new user volume to iOS
   - Target effect size precision
   - Run-of-experiment risks (OS updates, seasonal shifts)

---

## Ready for Next Steps

This framework is **ready to hand off to sample size estimation** once:
- [ ] Stakeholders confirm the minimum meaningful effect (3–5 pp or alternative)
- [ ] Guardrail thresholds are locked (e.g., max acceptable Day 1 retention drop)
- [ ] Expected baseline is confirmed from retrospective data (current first-session lesson start rate for iOS cohort)

After those confirmations, use **estimate-sample-size** to determine experiment duration and **design-experiment-plan** to finalize segment and variant logic.
