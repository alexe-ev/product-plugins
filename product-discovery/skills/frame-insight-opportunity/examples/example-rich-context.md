## Input

Product: Finly — a B2C mobile app for personal finance.

Validated insights from 10 user interviews:
1. Users who set a savings goal in the first 3 days retain significantly better — goal-setting is the mechanism that turns the app from a ledger into a progress tool.
2. Spend categorisation without forward-looking context creates a judgment experience, not a control experience — users see what went wrong but have no path to what to do next.
3. Finly has no built-in re-entry trigger — retained users created their own ritual; churned users had nothing to return to.
4. Payday is a high-motivation moment for financial engagement that the product is not capitalising on.
5. Financial anxiety is the primary emotional context of use — the product either reduces it or amplifies it depending on whether the user has a savings goal.

Business goal: Improve Day 14 retention from 22% to 35%. Primary segment: Anxious Planner persona (goal-setting, proactive, anxiety-driven).

## Expected output

Opportunity 1:
- HMW statement: How might we make savings goal-setting feel immediate and meaningful in the first session, so that new users have a compelling reason to return the next day?
- Source insight: Users who set a savings goal in the first 3 days retain significantly better — goal-setting is the activation mechanism.
- Affected segment: All new users; highest impact for Anxious Planner persona.
- Potential impact: High — directly addresses the primary behavioural differentiator between retained and churned users. Closing the goal-setting gap in the first session could materially shift Day 14 retention.
- Evidence quality: Data-informed — consistent pattern across 10 interviews; directionally corroborated by product usage data.
- Risks: A trivially easy goal (e.g., "save £1") may not create the same motivational effect as a meaningful one. Goal quality may matter as much as goal presence.
- Suggested next step: Formulate experiment hypothesis → test a goal-setting prompt at onboarding step 2 with a control group that receives no prompt.

Opportunity 2:
- HMW statement: How might we give users a clear forward-looking action after identifying overspend, so that the app feels like a guide rather than a judge?
- Source insight: Spend categorisation without forward-looking context creates a judgment experience — users see what went wrong but not what to do next.
- Affected segment: New users; Passive Tracker persona at highest churn risk.
- Potential impact: Medium — addresses a specific emotional churn trigger, but impact on overall retention is uncertain without more data on how many users experience this as a primary disengagement cause.
- Evidence quality: Data-informed — 5 of 10 users cited this pattern; churned users disproportionately used negative emotional language around spend tracking.
- Risks: Recommendations may feel intrusive or paternalistic if not carefully framed. Risk of adding cognitive load at a moment when users are already anxious.
- Suggested next step: Qualitative prototype test — show users a "what to do next" module after overspend categorisation and observe emotional response before committing to build.

Opportunity 3:
- HMW statement: How might we create a consistent payday re-entry moment for users, so that returning to Finly becomes a natural part of the pay-period ritual rather than an occasional event?
- Source insight: Finly has no built-in re-entry trigger — retained users invented their own ritual; churned users had nothing to return to. Payday is a high-motivation moment not yet capitalised on.
- Affected segment: All new users; highest impact for Anxious Planner persona who already has a payday-anchored mental model.
- Potential impact: High — could create a habitual return trigger for a large portion of the new user cohort and extend the engagement window beyond the first week.
- Evidence quality: Data-informed — 4 of 10 users mentioned payday spontaneously; retained vs. churned ritual split consistent across all interviews; no current product feature addresses this moment.
- Risks: Notification fatigue if not personalised or well-timed. Requires reliable bank sync data to detect payday accurately. iOS notification permissions add friction to implementation.
- Suggested next step: Formulate experiment hypothesis → test a payday check-in push notification with a goal progress summary vs. a control group with no payday notification.
