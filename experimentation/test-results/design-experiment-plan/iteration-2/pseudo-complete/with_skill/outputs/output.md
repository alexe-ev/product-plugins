# Experiment Plan: Feed Ranking Algorithm Optimization

**Plan Status:** ⚠️ PARTIAL SKELETON — NOT EXECUTION-READY

This plan has substantial gaps that block launch readiness. The inputs contain several vague specifications that must be resolved before implementation.

---

## Objective
Evaluate whether a personalized relevance-ranked feed improves user engagement compared to chronological ordering.

---

## Hypothesis
If we rank the home feed by predicted personal relevance score for active users, engagement will improve because personalized content should reduce friction in finding valuable posts.

---

## Variants

**Control:**
Current chronological feed ordering

**Test:**
Home feed ranked by predicted personal relevance score

---

## Target Audience
Active users (defined as: users who opened the app at least once in the last 30 days)

### Eligibility rules
- Randomize at user level
- Include both new and returning users within the 30-day active window
- No exclusions specified yet (consider: beta testers, internal users, users on outdated app versions)

---

## Metrics

### Primary Metric: ⚠️ NOT OPERATIONALIZED

**Current definition:** "Engagement"

**Problem:** This is too vague to measure, compare, or act upon. Engagement could mean:
- Daily active users (DAU)
- Session count
- Session length
- Number of posts viewed
- Number of posts interacted with (likes, comments, shares)
- Time spent in feed
- A composite metric combining multiple signals

**Action required:** Define the exact event(s) or formula before launch. Examples:
- "Posts viewed per session" (a specific interaction event)
- "Average session length in feed (seconds)"
- "Like/comment/share count per user per day"
- A named composite metric (e.g., "engagement score = 0.5×posts_viewed + 0.3×interactions + 0.2×session_length")

---

### Secondary Metrics
- Session length (measured how? seconds in app, seconds in feed specifically?)
- Content interactions (which interactions count? likes only, or likes + comments + shares?)

**Note:** These are partially operationalized but should be clarified to match primary metric scope.

---

### Guardrails (Recommended)
Consider adding:
- Feed load time (ensure ranking doesn't slow the app)
- User churn rate (ensure personalization doesn't drive users away)
- Help/support contact rate (ensure users aren't confused by the new order)
- Negative content exposure (if applicable, ensure algorithm doesn't show harmful content disproportionately)

---

## Success Threshold: ⚠️ NOT DEFINED

**Current definition:** "Significant improvement"

**Problem:** "Significant" is subjective and cannot be used to make a go/no-go decision. You need a numeric minimum detectable effect (MDE) or a percentage threshold.

**Action required:** Define one of these before launch:
- Minimum meaningful effect (e.g., "5% relative uplift in engagement rate")
- Absolute threshold (e.g., "session length must increase by at least 45 seconds")
- Statistical significance threshold (e.g., "p < 0.05")
- Business threshold (e.g., "engagement must increase by at least 10% to justify engineering effort")

### Current decision rules (vague):
- "Ship if engagement goes up"
- "Don't ship if engagement goes down"

**Problems with these:**
- "Goes up" could mean +0.1%, which may be noise
- "Goes down" is too binary—what if the metric is flat?
- No stopping rule for inconclusive results
- No guidance on statistical power (how confident must you be?)

---

## Sample Size & Duration

**Provided:**
- Sample size: ~20k users (based on previous experiment)
- Duration: 2 weeks

**Issues to resolve:**
- Is 20k sufficient for the chosen primary metric? This depends on the metric's variance and your desired statistical power.
- Will 2 weeks be enough to observe a stable pattern? (e.g., daily active users may fluctuate by day of week; 2 weeks may not capture the full cycle)
- Has this sample size been validated for the primary metric you finally choose?

---

## Stopping Logic: ⚠️ FLEXIBLE, NOT PRE-COMMITTED

**Current definition:** "The team will review results at the end of the 2 weeks and decide."

**Problem:** This is a "soft" decision rule, not a hard stopping criterion. It opens the door to:
- Decisions driven by narrative or early impressions rather than data
- Running longer if early results are inconclusive (risking peeking)
- Risk of p-hacking or cherry-picking favorable cuts of the data

**Action required:** Replace with a pre-committed, objective stopping logic. Examples:

Option 1 (Fixed duration):
"Run the test for exactly 2 weeks or until 20k users are assigned, whichever comes first. Review results once and make a binary decision."

Option 2 (Sequential with guardrail):
"Run in weekly cohorts. If after week 1 a guardrail is violated (e.g., feed load time increases >20%), stop immediately and investigate. Otherwise, continue to week 2."

Option 3 (Stopping boundary, optional):
"If at any point engagement *decreases* by >10% with p<0.05, stop and investigate. If results are inconclusive after 2 weeks, declare the test neutral and do not ship."

---

## Analysis Plan

**Planned approach:**
1. Compare primary metric (engagement) between control and test across the 2-week window
2. Check secondary metrics for side effects
3. Monitor guardrails throughout

**Missing details:**
- Will you segment results by user cohort (new vs. returning)?
- Will you control for day-of-week effects?
- How will you handle users who switch variants mid-test?
- Confidence level required (90%, 95%, 99%)?

---

## Outcomes & Actions

| Outcome | Condition | Action |
|---------|-----------|--------|
| **Success** | Engagement increases by ≥[X%] AND guardrails are healthy | Roll out to all users and begin post-launch monitoring |
| **Neutral** | Engagement change is within ±[X%] OR inconclusive | Hold; iterate on the ranking algorithm and retry |
| **Failure** | Engagement decreases by >[X%] OR guardrails violate thresholds | Revert to chronological feed; investigate root cause |

**Note:** The [X%] placeholders must be filled with your chosen success threshold.

---

## Risks & Validity Concerns

### 1. Unoperationalized Primary Metric
- **Risk:** Without a precise definition of "engagement," the team may interpret results differently or cherry-pick favorable slices of the data.
- **Mitigation:** Finalize metric definition and lock it before launch. Consider a composite metric combining multiple signals.

### 2. Vague Success Threshold
- **Risk:** "Significant improvement" invites post-hoc reasoning. The team may ship if engagement goes up 1% or hold if it goes up 5%, depending on mood.
- **Mitigation:** Set a numeric MDE before launch. Document the rationale (business value, statistical power, cost of change).

### 3. Flexible Stopping Logic
- **Risk:** Reviewing data ad-hoc at week 2 creates opportunity for p-hacking, peeking, or decision reversals. Results may be inconclusive, leading to extended deliberation.
- **Mitigation:** Pre-commit to a hard stopping rule. State upfront: "We will run for exactly 2 weeks and make one decision."

### 4. Sample Size May Be Undersized
- **Risk:** 20k users may not provide sufficient power if the expected effect is small or if the engagement metric is high-variance.
- **Mitigation:** Validate sample size using a power analysis based on your chosen primary metric and MDE.

### 5. Duration May Not Capture Weekly Cycles
- **Risk:** 2 weeks may not span a full week-week-end cycle variation. Some users may behave differently on weekends.
- **Mitigation:** Consider 3 weeks minimum, or stratify analysis by day of week.

### 6. No Segment Strategy
- **Risk:** If personalization works better for some user groups (new vs. returning, high-engagement vs. low-engagement), this may be masked in aggregate results.
- **Mitigation:** Plan to slice results by cohort pre-launch.

---

## Launch Blockers

The following gaps must be resolved before this plan becomes execution-ready:

1. **Primary Metric Definition** — "Engagement" must be operationalized as a specific event, formula, or named composite metric.
2. **Success Threshold** — "Significant improvement" must be replaced with a numeric minimum detectable effect (e.g., ±5% relative uplift).
3. **Stopping Logic** — "The team will review and decide" must be replaced with a pre-committed, objective stopping rule.
4. **Secondary Metric Clarity** — "Session length" and "content interactions" should be precisely defined to match scope and context.
5. **Sample Size Validation** — Confirm that 20k users and 2 weeks will provide sufficient statistical power for the chosen primary metric.

---

## Next Steps

1. **Metric Definition Workshop:** Align the team on a single, precise definition of engagement (event-level or composite).
2. **Threshold Setting:** Based on business impact and power analysis, set a minimum detectable effect.
3. **Stopping Rule Documentation:** Write a one-paragraph stopping rule that the team agrees to in advance.
4. **Statistical Review:** Validate sample size and duration assumptions using power analysis.
5. **Re-Review:** Once gaps 1–4 are resolved, resurface this plan for final launch approval.

---

## Summary

This plan captures the core experiment structure (hypothesis, variants, audience, rough metrics, sample size, and duration), but it **is not execution-ready** because three critical gaps block launch:

- The primary metric is unoperationalized.
- The success threshold is not numeric.
- The stopping logic is not pre-committed.

Resolve these gaps and this plan becomes solid. Without them, the team risks making data-driven-sounding decisions that are actually just narrative-driven.
