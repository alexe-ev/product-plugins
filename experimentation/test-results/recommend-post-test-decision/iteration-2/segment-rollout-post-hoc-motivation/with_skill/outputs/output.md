## Recommended action

Do not pursue a segment rollout based on this post-hoc analysis. Instead, treat the new-user finding as a hypothesis for a fresh experiment.

## Why this action is appropriate

The overall result was not statistically significant (p=0.09), and the team's proposal to roll out to new users only is based on a post-hoc segment breakdown—a high-risk analysis pattern that inflates false positive risk.

### Key concerns

**1. Post-hoc slicing invalidates the p-value**
The team observed a non-significant overall result and then analyzed segments after the fact. The p=0.011 in the new-user segment emerged from this exploratory analysis, not from a pre-registered hypothesis. Post-hoc segment analysis multiplies the number of statistical comparisons and dramatically increases the false positive rate. The apparent p-value of 0.011 does not reflect the actual probability of a false positive when considering the implicit multiple comparisons.

**2. The proposed segment rollout contradicts the pre-registered hypothesis**
The experiment was designed to test whether "a clearer pricing presentation will increase plan upgrade rate" for all users. The new-user effect was not the stated hypothesis. Pivoting to a segment rollout based on post-hoc discovery is a form of p-hacking that undermines the validity of the evidence.

**3. The null result in existing users does not confirm safety**
A p-value of 0.87 in the existing-user segment is simply consistent with no effect. It does not validate the design change as "safe"—that framing treats absence of evidence as evidence of absence. The existing-user segment is numerically comparable in size to the new-user segment, so the effect is clearly not uniform across the business.

**4. The effect may not replicate**
Segment findings from exploratory analysis have high replication failure rates, especially when the overall result was null. The 3.6pp effect in new users is striking, but it emerged from a small pool of implicit comparisons.

## Risks

- Rolling out to new users based on this analysis risks building the new design into production for a cohort where the effect may not hold in a prospective test
- The false positive risk is substantially higher than the reported p-value suggests
- If the effect does not replicate, the rollout becomes technical debt and potential user friction

## What should happen next

1. **Design a fresh, pre-registered experiment** with new users as the explicitly defined target population
2. Include the hypothesis about new-user responsiveness (e.g., "New users with less context about pricing will benefit more from clearer presentation")
3. Power the experiment for the new-user segment size, not the overall population
4. Specify the analysis plan in advance, including what constitutes a win
5. Run the experiment and evaluate results against the pre-registered plan
6. Only pursue rollout if the new experiment confirms the effect

## Missing business inputs that limit recommendation strength

- Why new users might respond differently (is this a hypothesis or a surprise?)
- Whether the team has capacity to run a follow-up experiment
- Whether the redesign introduces implementation risk or maintenance burden
- How quickly new users are acquired (i.e., how much business value hangs on this)
