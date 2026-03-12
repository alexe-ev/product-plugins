# Experiment Plan: Smart Send Time for Push Notifications

## Objective
Increase 7-day notification click-through rate by personalizing push notification send times to each user's historical peak activity window.

## Hypothesis
If we send push notifications at each user's historically most-active hour (smart send) instead of a fixed 10am broadcast, we expect 7-day notification click-through rate to increase, because personalized timing reduces interruption friction and aligns notifications with natural engagement windows.

## Variants

**Control:** Fixed 10am broadcast send time for all opted-in users

**Test:** Smart send time based on individual user's historical peak activity window (derived from 7+ days of app activity data)

## Target Audience & Eligibility

**Segment:** All iOS and Android users who have push notifications enabled

**Eligibility criteria:**
- Must have push notifications enabled
- Must have at least 7 days of app activity history (required for the smart send time model to generate accurate predictions)

**Rationale:** Users without 7+ days of history cannot have a reliable peak activity window, making the test variant invalid for that segment.

## Metrics

**Primary metric:**
- 7-day notification click-through rate (CTR): percentage of delivered notifications clicked within 7 days of receipt

**Secondary metrics:**
- 7-day DAU/MAU ratio: measure retention impact
- Notification opt-out rate: measure user preference shift

**Guardrails (must not degrade):**
- Notification delivery failure rate: must not increase by more than 1 percentage point above control
- App crash rate: must not double above control baseline

## Minimum Meaningful Effect & Success Threshold

**Minimum meaningful effect:** +10% relative improvement in 7-day CTR

**Success threshold:**
- 7-day CTR improves by ≥+10% relative AND
- All guardrails remain healthy (delivery failure ≤+1pp, crash rate ≤2x baseline)

**Confidence level:** 95% statistical significance

## Sample Size & Duration

**Sample size:** 45,000 users per group (control and test)

**Expected duration:** 3 weeks

**Total experiment population:** 90,000 users

## Stopping Logic

**Standard stopping:** Run the full 3-week duration to reach target sample size, unless emergency conditions trigger early stop.

**Emergency stopping conditions:**
- Notification delivery failure rate rises >2 percentage points above control, OR
- App crash rate more than doubles above control baseline

**Rationale:** Early stopping only for severe operational issues; statistical stopping is not warranted given the 3-week timeline and fixed sample size already estimated.

## Analysis Plan

1. **Intent-to-treat analysis:** All randomized users included, regardless of activity after randomization
2. **Primary metric:** Calculate 7-day CTR for each group; compare using difference-in-means t-test at 95% confidence
3. **Secondary metrics:** Compare DAU/MAU ratio and opt-out rate; flag material changes even if not statistically significant
4. **Guardrails:** Monitor delivery failure rate and crash rate continuously; stop if thresholds breached
5. **Segment analysis:** If directional lift exists, examine CTR uplift by user activity level to understand model accuracy

## Success, Neutral, and Failure Outcomes

### Success
**Outcome:** 7-day CTR improves ≥+10% relative AND guardrails healthy

**Action:**
- Roll out smart send time feature to all eligible users
- Sunset the fixed 10am broadcast approach
- Monitor week-over-week retention and engagement post-rollout
- Consider extending smart send to other notification types

### Neutral (Partial Uplift)
**Outcome:** 7-day CTR improves by +5–9% relative (below success threshold but directional)

**Action:**
- Do not roll out yet
- Investigate model accuracy: segment users by activity level to see if smart send underperforms for low-activity users
- Consider refining the peak activity window logic (e.g., broader window, fallback rules for noisy data)
- Retest with refined model in 4–6 weeks

### Failure
**Outcome:** 7-day CTR flat or negative OR opt-out rate increases materially OR guardrails breached

**Action:**
- Do not roll out
- Investigate root cause: was delivery timing incorrect? Did model predict wrong windows? Did users find more interruption, not less?
- Return to hypothesis validation; the friction reduction assumption may not hold
- Consider alternative levers (notification content, frequency capping, user segmentation rules)

## Operational & Validity Risks

1. **Model accuracy dependency:** Smart send relies on historical peak activity windows. For new users or those with irregular patterns, the model may misclassify peak activity, leading to poor send timing and false negatives. Mitigation: Validate model precision on holdout user cohorts before and after launch; use a fallback rule (e.g., revert to 10am for low-confidence predictions).

2. **Novelty effect:** Users may initially engage more with notifications arriving at unexpected times (surprise effect) rather than due to genuine friction reduction. This could decay over time post-rollout. Mitigation: Monitor engagement by week post-launch to detect novelty decay; plan for retention impact at 4+ weeks.

3. **Delivery timing variance:** Differences in time zone, device sleep scheduling, or carrier delays could cause test variant to have higher delivery latency, confounding the send-time effect. Mitigation: Segment analysis by time zone and device OS; track delivery latency as a secondary metric.

4. **Selection bias from eligibility rule:** Users with 7+ days of activity history differ systematically from new users (more engaged, higher retention baseline). Results may not generalize to new user onboarding push strategies. Mitigation: Plan for separate test of smart send on new users with bootstrapped or default activity windows.

5. **External time-based confounds:** Seasonal, day-of-week, or event-driven changes in user activity during the 3-week test period could bias CTR estimates. Mitigation: If major events occur during test, capture them in post-hoc analysis and consider repeat testing.

## Launch Readiness Checklist

- ✓ Hypothesis clearly defined and testable
- ✓ Control and test variants distinct and implementable
- ✓ Target segment and eligibility criteria specified (7+ day activity requirement)
- ✓ Primary metric unambiguous (7-day CTR)
- ✓ Secondary metrics and guardrails identified
- ✓ Success threshold quantified (≥+10% relative, 95% confidence)
- ✓ Sample size and duration already estimated
- ✓ Stopping logic defined (run full 3 weeks, emergency stop only for delivery/crash issues)
- ✓ Decision rules clear for success, partial, and failure outcomes
- ✓ Key risks identified and mitigation strategies outlined

**Plan status:** Execution-ready. No critical fields missing. Proceed to implementation handoff.
