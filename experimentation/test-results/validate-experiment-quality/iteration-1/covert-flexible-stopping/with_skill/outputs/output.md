# Experiment Quality Audit: New Onboarding Email Sequence

## Quality Verdict
**Low to Manageable Confidence**

This experiment exhibits a critical procedural flaw that weakens trust in the result, despite adequate sample size and allocation balance.

## Major Risks

1. **Flexible Stopping (Primary Risk)**
   - The experiment was planned for 21 days but extended to 25 days
   - Stopping decision was explicitly outcome-dependent: "Results weren't conclusive enough at the 3-week mark, so we gave it a few more days"
   - The team stopped when "results looked clearer" on day 25
   - This is a classic case of peeking and acting on interim results

2. **Outcome-Dependent Procedure**
   - Sample size was predefined (12,000 per group), which is good
   - However, the stopping rule was NOT predefined
   - The team monitored daily and made a stopping decision based on how conclusive the results appeared
   - This violates the principle that stopping should follow a predetermined rule, not result appearance

3. **Reduced Trust in Statistical Interpretation**
   - Classical p-value interpretation assumes a fixed stopping rule
   - When stopping is flexible and outcome-dependent, p-values become inflated
   - The team may have captured noise and stopped when results temporarily favored the treatment

## Reliability Level
**Medium-Low**

The experiment has good structural features (traffic balance, consistent assignment, no external events, correct metric), but the procedural violation significantly undermines confidence.

## Fatal vs. Manageable Issues

**Manageable but Serious:**
- The flexible stopping is not necessarily fatal, but it creates a validity risk
- The 4-day extension is relatively modest (21 vs. 25 days)
- However, the explicit statement that stopping was triggered by result appearance is a red flag

## Recommendation
**Treat Cautiously**

This result should not be treated as a standalone justification for the change. Before implementing:
1. Verify the result through a fresh rerun with predefined sample size AND stopping rule
2. If results are strong in the rerun, the evidence becomes more trustworthy
3. Use the 25-day result as exploratory evidence, not confirmatory evidence

## Missing Procedural Evidence
- Whether a multiple-comparison correction was applied (unlikely)
- Whether other metrics or segments were also monitored and acted upon
- Statistical power and actual uplift size at day 21 vs. day 25
