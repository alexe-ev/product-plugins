**Smart Send Time Push Notification Experiment Plan**

**1. Hypothesis**
Sending push notifications at each user's historically most-active hour will increase 7-day notification click-through rate compared to a fixed 10am broadcast, because personalized timing reduces interruption friction and aligns with when users are naturally engaged with the app.

**2. Experiment Design**

**Control Group (50%):** Fixed 10am UTC broadcast to all opted-in users with push enabled

**Test Group (50%):** Smart send time notifications delivered during each user's historical peak activity window (determined by analyzing the past 7 days of app session data)

**3. Target Audience & Eligibility**
- All iOS and Android users with push notifications enabled
- Minimum 7 days of app activity history (required to establish reliable historical activity patterns for the send-time model)
- Excludes users without sufficient data to calculate peak activity windows
- Sample: 45,000 users per group (90,000 total)

**4. Primary Metric**
7-day notification click-through rate (CTR): clicks on notifications / notifications delivered

**5. Secondary Metrics**
- 7-day DAU/MAU ratio (engagement persistence)
- Notification opt-out rate (user comfort with notification frequency/timing)

**6. Guardrails & Safety Thresholds**
- Notification delivery failure rate: must not exceed control by more than 1 percentage point
- App crash rate: must not increase by more than 100% (double the baseline)
- If delivery failures exceed control by >2pp or crash rate doubles, trigger emergency stop

**7. Success Threshold**
- Primary success: CTR improves by ≥+10% relative to control, statistically significant at 95% confidence
- Minimum meaningful effect size: +10% relative improvement

**8. Test Duration & Stopping Logic**
- Full 3-week run (21 days) unless emergency triggers
- Emergency stop conditions: delivery failure rate >2pp above control OR app crash rate doubles baseline
- No interim analyses; run to completion unless safety guardrails breached

**9. Decision Framework**

| Outcome | Action |
|---------|--------|
| CTR ≥+10% and guardrails healthy | Full rollout to all eligible users |
| CTR improvement 5–9% | Retest with refined model (e.g., expanded history window, regional factors) |
| CTR ≤0% or opt-out rate increases materially | Archive; investigate friction points; do not roll out |

**10. Operational Considerations**

**Data & Model Dependency:** Success depends on the accuracy of the historical activity model. Users with inconsistent activity patterns may receive suboptimal send times. Recommend validating model calibration on holdout users pre-launch.

**Timezone Handling:** Ensure peak activity windows are calculated and delivered in user's local timezone to avoid edge cases (e.g., late-night sends if 10am is in a different timezone).

**Novelty Effect:** Initial uplift may include a novelty boost from personalized timing; monitor decay in weeks 2–3 to assess sustained impact.

**Cohort Stability:** Ensure users remain in their assigned group for the full 3 weeks (no switches mid-experiment).
