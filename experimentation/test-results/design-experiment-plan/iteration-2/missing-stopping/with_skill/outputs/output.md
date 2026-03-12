## Experiment Plan: Trial-to-Paid Conversion with Personalised Use-Case Checklist

### Objective
Increase trial-to-paid conversion rate by providing new users with a personalised use-case checklist during their trial period, allowing them to clearly see value milestones and progress toward adoption.

### Hypothesis
If we show a personalised use-case checklist on the dashboard during the trial period, we expect trial-to-paid conversion rate to increase, because users who see clear value milestones are more likely to recognize product fit and convert to paid plans.

### Variants

**Control:**
Current generic trial experience (dashboard without checklist)

**Test:**
Dashboard with personalised use-case checklist displayed prominently during trial period

### Target Audience
All new users who start a free trial on desktop web. Desktop web only in this iteration. (Note: future versions may expand to mobile.)

### Primary Metric
- **Trial-to-paid conversion rate** (measured at day 14 of trial period)
  - Definition: (Paid conversions / Trial starters) × 100
  - Measurement window: Day 0–14 of trial

### Secondary Metrics
- **Checklist completion rate** (% of test group who complete all checklist items)
- **Feature activation rate** (% of test group with ≥3 features used within 7 days)

### Guardrails
- **Support ticket rate:** Must not increase materially vs. control
- **Trial abandonment rate:** Must not increase vs. control

### Success Thresholds
- **Primary metric success:** Conversion rate increases ≥+2 absolute percentage points (from 18% baseline to ≥20%) at 95% confidence
- **Guardrail health:** Both guardrail metrics remain stable or improve vs. control

### Sample Size & Duration
- **Sample size:** 2,500 users per group (already estimated)
- **Expected duration:** *[MISSING FIELD]* — To calculate expected run length, we need:
  - Current trial sign-up volume or daily new user rate
  - Duration = (2,500 × 2 groups) / (daily new trial starters)

  Please provide daily trial starter volume to estimate calendar duration.

### Stopping Logic
**[MISSING FIELD — BLOCKS LAUNCH]**

The experiment lacks a predefined stopping rule. Before launch, the team must decide:

1. **Run to fixed sample size?**
   - Run until 2,500 per group, regardless of calendar time

2. **Run to fixed calendar date?**
   - Run for a fixed number of days (e.g., 30 days, 60 days), then analyze regardless of sample size

3. **Early stopping rule?**
   - Stop early if conversion decreases significantly or guardrails break
   - If so, define the threshold (e.g., conversion drops >3pp, support tickets spike >20%)

4. **Combination?**
   - Run until sample size OR calendar date, whichever comes first

**Recommendation:** Suggest the team confirm which rule applies and document it before launch. This is a validity blocker.

### Analysis Plan
1. **Primary outcome:** Test for statistical significance at 95% confidence using a 2-sample proportions test
2. **Secondary outcomes:** Report completion and activation rates by group; flag if either shows strong directional difference
3. **Guardrail outcomes:** Compare support ticket rate and abandonment rate; flag if either worsens materially
4. **Holdout analysis:** Track cohort performance over days 0–7, 7–14 to identify timing effects

### Decision Rules

**If threshold met + guardrails healthy:**
- Full rollout to all new trial users
- Measure impact on company-wide conversion and retention

**If positive but below threshold (≥+1pp but <+2pp):**
- Iterate on checklist content based on user feedback and engagement patterns
- Run follow-up test with improved version
- Do not roll out; hold pending next iteration

**If neutral or negative:**
- Discontinue checklist variant
- Return to current trial flow
- Document learnings about user value perception

**If guardrails worsen (support ticket rate or abandonment rate increases):**
- Halt test immediately
- Investigate root cause
- Revert to control flow
- Iterate design before next test cycle

### Launch Readiness

**Fields present and well-defined:**
✓ Hypothesis
✓ Control and test variants
✓ Target segment (desktop web new trials)
✓ Primary metric (conversion rate at day 14)
✓ Secondary metrics (checklist completion, feature activation)
✓ Guardrails (support tickets, abandonment)
✓ Minimum meaningful effect (+2pp)
✓ Success threshold (≥+2pp at 95% confidence)
✓ Sample size (2,500 per group)
✓ Decision rules (full rollout, iterate, discontinue, emergency halt)

**Missing or unresolved fields that block launch:**
- **Stopping logic** — Must define before launch (fixed sample? fixed date? emergency stops only?)
- **Estimated duration** — Dependent on traffic; requires daily trial sign-up volume

### Risks & Operational Considerations
1. **Checklist relevance:** If the personalised logic does not accurately segment users by use case, checklist may feel generic and fail to drive conversion
2. **Mobile exclusion:** Desktop-only test limits generalizability; may need follow-up mobile test
3. **Seasonality:** Confirm test runs across stable user acquisition period (avoid major product launches, pricing changes, or marketing campaigns)
4. **Learning effect:** Day 14 conversion may not reflect day-30 or day-60 behavior; consider delayed retention measurement
