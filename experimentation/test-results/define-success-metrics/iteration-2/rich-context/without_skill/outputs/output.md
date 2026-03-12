# Success Metrics Framework: Weekly Spending Summary Experiment

## Experiment Overview
**Hypothesis**: If we show users a weekly spending summary inside the app, more users will stay active past day 30 — because they'll have a reason to return and check their progress.

**Business Goal**: Improve 30-day retention without increasing notification opt-outs or creating anxiety around spending habits.

---

## Primary Success Metrics

### 1. **30-Day Retention Rate** (PRIMARY KPI)
- **Definition**: % of users who engaged with the app on at least 1 day during days 1-7 who return on day 30+
- **Success Threshold**: ≥5% relative increase from control group
- **Rationale**: This directly measures the hypothesis — the spending summary should give users a compelling reason to return
- **Collection**: Track unique active users on day 30+ in both cohorts
- **Direction**: Higher is better

### 2. **7-Day Retention Rate** (LEADING INDICATOR)
- **Definition**: % of Day 1 active users who return on day 7+
- **Success Threshold**: ≥3% relative increase from control
- **Rationale**: Earlier signal of engagement patterns; helps diagnose if the feature drives sustained usage from day 1
- **Direction**: Higher is better

---

## Secondary Success Metrics

### 3. **Feature Engagement**
- **Weekly Summary Views**: Average views per user per week (treatment group only)
  - **Success Threshold**: ≥70% of treatment group views summary ≥1x per week
  - **Rationale**: Validates that users see and engage with the feature

- **Return Frequency on Feature Days**: Among users who view the summary, days of app activity in the following 7 days
  - **Success Threshold**: Users viewing summary have ≥40% more session days than non-viewers in same cohort
  - **Rationale**: Checks if the summary is driving repeat visits, not just awareness

### 4. **Session Intensity**
- **Avg Sessions per Active Day**: For day 30+ users (treatment vs. control)
  - **Success Threshold**: No decline in session count (maintain parity)
  - **Rationale**: Ensures we're not seeing users return *less frequently* per day, just returning on more days

- **Avg Session Duration**: Time spent per session on day 30+
  - **Success Threshold**: No statistically significant decrease
  - **Rationale**: Spending summary shouldn't displace other productive app usage

---

## Guardian Metrics (Must Not Regress)

### 5. **Notification Opt-Out Rate**
- **Definition**: % of users who disable push/in-app notifications within 30 days of install
- **Success Threshold**: No increase relative to control (≤ control opt-out rate)
- **Rationale**: Directly addresses risk of over-notifying users about spending
- **Notes**: Track separately for each notification channel if applicable

### 6. **Anxiety/Negative Sentiment Proxy Metrics**
- **In-App Feedback Sentiment**: If your app has built-in feedback, track % of negative mentions of "summary," "spending," or "review"
  - **Success Threshold**: No statistically significant increase in negative sentiment

- **Support Tickets Related to Spending Anxiety**: Volume of support requests mentioning stress, concerns, or anxiety about their spending data
  - **Success Threshold**: No increase in per-user support volume (treatment vs. control)

- **Feature Avoidance**: % of treatment users who have the summary visible but never tap/view it
  - **Success Threshold**: <40% permanent avoidance (rest eventually engage)
  - **Rationale**: High avoidance suggests the feature is causing discomfort

---

## Exploratory Metrics (Learning Goals)

### 7. **Segment-Level Retention**
- **By Spending Confidence**: Retain users by their initial spending profile:
  - Heavy spenders vs. light spenders
  - Frequent app users vs. infrequent
  - *Insight Goal*: Identify if summary resonates differently by user segment

- **By Feature Interaction Pattern**: Users who view summary early (day 1-3) vs. late (day 15+)
  - *Insight Goal*: Understand optimal timing for feature introduction

### 8. **User Retention Cohorts at Key Milestones**
- Day 7, 14, 21, 30 retention (not just day 30)
  - *Insight Goal*: See where treatment and control diverge; helps refine feature timing

### 9. **Week-over-Week Engagement Trends**
- Track when users drop off (at what point does control group fall behind?)
- Measure 30-day users' activity in their final week (spike, flatline, or decline?)
  - *Insight Goal*: Is the summary effect sustained or does engagement decay?

---

## Anti-Metrics (What Success is NOT)

- ❌ High retention driven by increased notifications (defeats business goal)
- ❌ Users viewing the summary but with lower session count/duration per day (passive engagement only)
- ❌ Retention gains limited to early cohorts that gradually diminish
- ❌ Disproportionate retention gains in only one segment (suggests feature is niche, not universally effective)

---

## Statistical Rigor

### Sample Size & Duration
- **Minimum Sample**: 10,000+ users per cohort to detect ≥5% relative uplift with 80% power
- **Experiment Duration**: Run for full 30 days minimum (recommend 35-42 days to allow sufficient day 30 observations)
- **Confidence Threshold**: 95% (p < 0.05)

### Multiple Comparisons
- **Primary Metric**: 30-day retention (one-tailed test, directional)
- **Secondary Metrics**: Apply Bonferroni correction or false discovery rate (FDR) control to guardians + 2-3 key secondary metrics
- **Exploratory Metrics**: Report without correction (transparency that these are hypothesis-generating)

### Guardrail Thresholds
- **Notification Opt-Outs**: Must remain within ±10% of control rate; if exceeds, halt experiment
- **Session Duration**: Must not decline >10% relative to control
- **Support Volume**: Must not increase >15% relative to control

---

## Decision Rules

### Experiment Succeeds If:
1. **30-day retention** shows ≥5% relative improvement (statistically significant) AND
2. **Notification opt-out rate** does NOT increase meaningfully AND
3. **Session metrics** maintain baseline or improve (no evidence of anxiety displacement)

### Experiment Fails If:
- 30-day retention shows no lift or regresses
- OR opt-out rate increases significantly
- OR support volume spikes with anxiety-related complaints

### Investigate Further If:
- Retention improves but opt-outs also increase (may need messaging/UX refinement)
- Retention improves only in specific segments (consider launching with targeting)
- Feature engagement is high but retention doesn't follow (feature may be interesting but not motivating)

---

## Monitoring Cadence During Experiment

- **Daily**: Opt-out rate, support ticket volume (watch for red flags)
- **Every 7 Days**: Engagement metrics, Day 7 retention snapshot
- **End of Experiment**: Full 30-day retention analysis, segment deep-dives

---

## Success Criteria Summary Table

| Metric | Threshold | Type | Priority |
|--------|-----------|------|----------|
| 30-day retention | +5% relative | Primary | Must Achieve |
| Notification opt-outs | No increase | Guardian | Must Not Regress |
| Anxiety/sentiment | No increase | Guardian | Must Not Regress |
| Weekly summary views | ≥70% of treatment | Secondary | Contextual |
| Session duration (day 30+) | No decline | Secondary | Contextual |
| 7-day retention | +3% relative | Leading Indicator | Directional |

---

## Next Steps

1. **Define baseline metrics** from historical control cohort (last 60 days of user installs)
2. **Set up tracking** for each metric in your analytics stack
3. **Configure alerts** for guardian metrics (opt-outs, support spikes)
4. **Create experiment variants** (treatment with summary vs. control without)
5. **Establish holdout strategy** (recommend 10-20% holdout to monitor control over time)
6. **Plan for segmentation analysis** — instrument data to slice by spending habits, engagement patterns
7. **Document edge cases** (e.g., what counts as a "view," how to handle uninstalls/reinstalls)

---

## Questions to Consider Before Launch

- **Frequency**: How often should the summary update/refresh? Weekly cadence is implicit — validate this drives weekly returns.
- **Placement**: Will summary be prominent (tab, home screen) or discoverable (buried in menu)? Placement affects discovery rate and perceived importance.
- **Privacy**: Is spending data sensitive? Confirm users see summaries only for their own data.
- **Timing**: Should summary notify users when available (violates opt-out guardrail) or silently wait for them to discover it?
- **Content**: What insights does the summary show? (Just totals? Trends? Alerts?) This shapes perceived utility and anxiety risk.

Clearer answers here will strengthen predictions around retention lift and anxiety risk.
