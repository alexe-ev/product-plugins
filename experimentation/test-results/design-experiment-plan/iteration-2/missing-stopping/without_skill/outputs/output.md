# Experiment Plan: Trial-to-Paid Conversion via Personalised Checklist

## Executive Summary
Your experiment is well-structured with clear hypothesis, metrics, and decision logic. However, there is **one critical gap that blocks execution readiness**: the plan lacks a defined **stopping rule** that specifies when the experiment should conclude.

## Confirmed Strengths
✓ **Hypothesis** — Clear, testable, and user-psychology-grounded
✓ **Segment & Variant Definition** — Desktop web, new trials, control/test clearly scoped
✓ **Primary & Secondary Metrics** — Conversion rate is correct lead metric; checklists completion and feature activation provide directional insights
✓ **Guardrails** — Support ticket rate and trial abandonment rate appropriately protect against negative spillovers
✓ **Sample Size** — 2,500 per arm is appropriate for detecting +2pp lift at 95% confidence
✓ **Decision Rules** — Rollout, iterate, or discontinue paths are clearly articulated

## Critical Missing Element: Stopping Rule
**The plan does not specify when the experiment ends.** This is a blocking issue. You must define one of:

1. **Fixed sample size approach** (most common): Stop when you reach 2,500 users per arm, then analyze.
   - *Question: What is your trial signup volume per day?* If 300/day, this is ~17 days per arm.

2. **Fixed calendar deadline**: Stop on a specific date (e.g., March 31, 2026) regardless of sample reached.

3. **Sequential testing with interim analysis**: Check after 50% of sample (1,250 per arm) with pre-defined rules to stop early if effect is very strong or futile.

4. **Emergency stop triggers**: Guardrail violations (e.g., support ticket rate increases >30%) trigger immediate halt.

**Right now, the plan is ambiguous.** Without a stopping rule, you won't know when to end the experiment, and you risk:
- Running indefinitely
- Peeking at results and making biased decisions
- Missing the opportunity to act on learnings

## Recommended Next Step
**Before launch, your team must agree on:**
- Primary stopping rule (sample size or date?)
- If sample size: confirm expected daily trial volume and target end date
- If date-based: confirm you'll have sufficient data by that date
- Emergency stop thresholds for guardrails

## Experiment Duration (Pending Stopping Rule Decision)
Once you decide, duration is easy to calculate:
- **If fixed sample:** (Sample size per arm × 2) ÷ (daily trial starts) = duration
- **If fixed date:** Already defined

**Example:** If 300 daily trial starts and fixed sample approach → (2,500 × 2) ÷ 300 = ~17 days to statistical completion

## Operational Readiness Checklist
- [ ] Hypothesis and metric approved by leadership
- [ ] Tech team can segment traffic (desktop web, new trials)
- [ ] Variant code deployed to staging (checklist UI ready)
- [ ] Analytics pipeline logs conversion events correctly
- [ ] **Stopping rule defined and agreed** ← REQUIRED BEFORE LAUNCH
- [ ] Guardrail monitoring dashboards live
- [ ] Sample size calculation validated by data team
