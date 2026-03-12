# Success Metrics: In-App Upgrade Prompt at Collaborator Limit

## Hypothesis
If we show an in-app upgrade prompt right after a user hits the collaborator limit on a free plan, we will increase paid conversions.

## Primary Metric
**Upgrade conversion rate among prompted users** — the proportion of free-tier users who see the collaborator limit prompt and subsequently purchase a paid plan within 14 days of being prompted.

### Why it is primary
The hypothesis directly targets paid conversions as the outcome. This metric measures whether the prompt achieves its intended effect: converting free users to paid. It is the closest measure to the stated goal and is causal to revenue impact.

## Secondary Metrics
- **Prompt engagement rate** — proportion of users who interact with the prompt (click, dismiss, or explore options) vs. those who ignore it
- **Time to upgrade** — days between prompt exposure and upgrade purchase
- **Upgrade rate by user segment** — conversion rates by company size, usage intensity, or other relevant cohorts
- **Feature adoption post-upgrade** — whether upgraded users actually use multiple collaborators in the weeks following upgrade
- **Upgrade plan type selected** — distribution of paid plan tiers purchased (if multiple tiers exist)

## Guardrail Metrics
- **User retention in control group** — ensure the control group (no prompt) does not have materially worse 30-day retention
- **Churn rate among prompted users** — proportion of prompted users who churn before upgrading
- **Support volume increase** — tickets related to "collaborator limit" or "upgrade" should not spike
- **Feature usage metrics** — time spent in-app should not decrease for prompted users (no negative user experience signals)
- **Prompt abandonment rate** — proportion of users who see the prompt and immediately churn

## Minimum Meaningful Effect
Not yet defined. This depends on:
- Current baseline upgrade conversion rate for free users
- Cost per acquisition for paid plans
- Average revenue per user (ARPU) for the free-to-paid funnel
- Company's threshold for test investment

**Recommendation**: Establish baseline conversion rate before experiment launch, then define minimum meaningful effect as 15-25% relative lift (requires data from product team).

## Success Threshold
- **Primary metric moves positively** by at least [X]% relative to control (baseline-dependent)
- **All guardrail metrics remain flat or improve** (no material degradation in retention or engagement)

## Neutral Zone
- Primary metric improvement is statistically insignificant or <10% relative lift
- Guardrails show minor degradation that is acceptable trade-off

## Failure Threshold
- Primary metric shows no improvement or declines vs. control
- Any guardrail metric shows material degradation:
  - Churn rate increases by >5% absolute
  - Retention drops by >10% relative
  - Support volume increases by >20%

## Interpretation Notes
1. **Timing matters**: The 14-day window assumes users decide to upgrade relatively quickly after hitting the limit. If users typically wait longer, extend the window to 30 days and monitor separately.

2. **Selection bias risk**: Users who hit the collaborator limit may already be high-engagement users more likely to upgrade. The control group definition is critical—compare against users who also hit the limit but did not see the prompt (not against all free users).

3. **Cannibalization possible**: Measure whether the prompt accelerates existing upgraders (who would have upgraded anyway) vs. converting new-to-paid users. Monitor time-to-upgrade shift in secondary metrics.

4. **Guardrails assume good UX**: If the prompt is poorly designed or confusing, it could drive churn. Guardrails are essential.

## Which Parts Are Provisional Due to Missing Context
- **Minimum meaningful effect size** — requires current baseline conversion rate and business cost/benefit analysis
- **Success and failure thresholds (numeric)** — require baseline metrics and statistical power calculations
- **14-day conversion window** — should be validated against typical user behavior data; may need adjustment to 7, 21, or 30 days
- **Definition of "upgrade"** — assumes full plan purchase; clarify if trial conversions or plan downgrades count
- **Segment-level expectations** — secondary metric thresholds for different user cohorts require segmentation strategy
- **Support volume guardrail threshold** — the "20%" increase threshold is illustrative; should be calibrated to current volume

## Recommended Next Steps Before Launch
1. Confirm baseline upgrade conversion rate for free users currently at collaborator limit
2. Define the precise 30/60/90-day cohort windows for measuring conversions
3. Establish statistical power requirements and calculate sample size
4. Design control group selection logic (users who hit limit but no prompt)
5. Specify prompt design and messaging to ensure guardrails are meaningful
6. Align on team risk tolerance and acceptable trade-offs in retention vs. conversion lift
