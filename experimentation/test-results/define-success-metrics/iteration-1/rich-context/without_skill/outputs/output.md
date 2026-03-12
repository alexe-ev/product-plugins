# Success Metrics Framework: iOS Onboarding Optimization Experiment

## Experiment Overview
**Hypothesis:** Reducing iOS onboarding from 5 steps to 3 will increase new-user activation (first lesson starts).
**Business Goal:** Increase new-user activation without hurting Day 1 retention.

---

## Primary Success Metrics

### 1. First Lesson Start Rate (Primary Activation Metric)
- **Definition:** % of new users who initiate their first lesson within the onboarding session
- **Calculation:** (Users who started lesson / Total new users in variant) × 100
- **Why it matters:** Directly measures the hypothesis—does reducing steps increase lesson starts?
- **Success criteria:** Statistically significant increase vs. control (recommend 2%+ lift minimum)
- **Tracking:** Track as both absolute completion rate and time-to-event

### 2. Onboarding Completion Rate
- **Definition:** % of new users who complete the full onboarding flow (all 3 or 5 steps)
- **Calculation:** (Users who completed / Total new users) × 100
- **Why it matters:** Validates that the 3-step flow is functional; lower completion doesn't necessarily indicate failure if step count decreased
- **Success criteria:** Maintain ≥75% completion rate (or show improvement)

### 3. Day 1 Retention Rate (Core Business Metric)
- **Definition:** % of new users who return and are active on Day 1 after signup
- **Calculation:** (Users active on Day 1 / Users who signed up) × 100
- **Why it matters:** Core business goal explicitly requires NOT hurting Day 1 retention
- **Success criteria:** No statistically significant decrease; ideally maintain or improve vs. control
- **Threshold:** Cannot declare success if Day 1 retention drops >1% (or your acceptable threshold)

---

## Secondary Success Metrics

### 4. Time to First Lesson (Velocity Metric)
- **Definition:** Median time from signup completion to first lesson start (in minutes)
- **Calculation:** Median([time_to_lesson] for all users who started a lesson)
- **Why it matters:** Tests if faster onboarding actually accelerates user progression
- **Success criteria:** 15-30% reduction vs. control expected

### 5. Onboarding Drop-off Rate by Step
- **Definition:** % of users dropping off at each step (for variant vs. control)
- **Calculation:** (Users who started step N but didn't complete) / (Users who started step N) × 100
- **Why it matters:** Identifies which steps cause friction; may show 3-step flow has better per-step retention
- **Success criteria:** Lower drop-off rates on remaining steps in the 3-step variant

### 6. Day 3 and Day 7 Retention (Extended Retention Check)
- **Definition:** % of new users who return on Day 3 and Day 7
- **Calculation:** (Users active on Day X / Users who signed up) × 100
- **Why it matters:** Ensures short-term activation doesn't trade off long-term engagement
- **Success criteria:** Maintain or improve vs. control (no decline)

---

## Guardrail Metrics (Must Not Regress)

### 7. Premium Conversion Rate (If applicable)
- **Definition:** % of new users who upgrade to premium within 7 days
- **Calculation:** (Users who converted / New users) × 100
- **Why it matters:** Ensures faster activation doesn't mean users skip setup that drives monetization
- **Success criteria:** No decrease >0.5% vs. control

### 8. Support Ticket Volume
- **Definition:** Support tickets filed per 1,000 new users in first 7 days
- **Why it matters:** Fewer onboarding steps might mean confused users reaching support
- **Success criteria:** No increase >10% vs. control

### 9. First Lesson Completion Rate
- **Definition:** % of users who started a lesson AND completed it (not just started)
- **Calculation:** (Users who completed first lesson / Users who started first lesson) × 100
- **Why it matters:** Confirms users aren't just starting lessons—they're actually engaging
- **Success criteria:** Maintain ≥60% completion rate

---

## Statistical Rigor & Testing

### Sample Size & Power
- **Recommended:** Run for minimum 2,000 new users per variant (control + treatment) for 80% statistical power at 95% confidence
- **Duration:** Run 2-4 weeks to capture full cohort behavior and account for day-of-week effects

### Multiple Comparisons
- **Primary metric:** Day 1 retention + first lesson start rate (treat as co-primary)
- **Adjust for multiple comparisons:** Use Bonferroni correction or pre-specify metrics hierarchy to avoid false positives
- **Significance level:** p < 0.05 for primary metrics

### Data Integrity
- Track user cohort by signup date to ensure clean Day 1, Day 3, Day 7 calculations
- Account for time zone differences if onboarding spans multiple days

---

## Success Criteria Summary

### ✅ Full Success
1. **Statistically significant increase** in first lesson start rate (2%+ lift, p < 0.05)
2. **No regression** in Day 1 retention (same or better, p > 0.05)
3. **Maintained or improved** Day 3/Day 7 retention
4. **No increase** in support tickets or other guardrails

### ⚠️ Qualified Success
- First lesson start rate improves but Day 1 retention declines by <0.5%
- Consider rollout with monitoring if business trade-off is acceptable

### ❌ Failure
- No improvement in first lesson start rate, OR
- Day 1 retention decreases by >1%, OR
- Guardrail metrics show concerning degradation

---

## Recommended Experiment Checklist

- [ ] Set minimum sample size: 2,000+ users per variant
- [ ] Define Day 1 activity threshold (e.g., "opened app" or "completed first lesson")
- [ ] Segment results by user cohort (acquisition source, geography, device OS) to ensure iOS-specific insights
- [ ] Set up real-time monitoring dashboard for key metrics
- [ ] Pre-register statistical analysis plan
- [ ] Plan rollback strategy if guardrail metrics breach
- [ ] Schedule decision meeting after 2 weeks or 2,000 users (whichever comes first)

---

## Notes for Implementation

1. **Hypothesis Testing:** This framework tests both directional (does onboarding improve activation?) and business-critical (does it preserve retention?) questions simultaneously.

2. **Mobile Context:** iOS-specific metrics are important—consider tracking if behavior differs significantly from Android onboarding (if you have parallel experiments).

3. **Confounding Variables:** Control for:
   - Seasonal signup trends
   - Any concurrent marketing campaigns
   - Feature releases in same period
   - iOS version/device type differences

4. **Iteration Path:** If experiment succeeds, consider A/B testing further optimizations (e.g., 2-step onboarding) as a follow-up.
