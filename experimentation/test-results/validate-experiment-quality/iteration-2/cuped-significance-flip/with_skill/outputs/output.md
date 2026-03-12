# Experiment Quality Validation: Simplified Notification Preferences UI

## Quality Verdict
**Limited-confidence verdict with a critical concern about statistical interpretation**

This experiment has strong procedural characteristics overall, but the team's decision to use the post-CUPED result as the primary basis for shipping requires scrutiny before acceptance.

## Procedural Quality Summary

### Strengths
- **Predefined sample size**: 9,000 per group (achieved)
- **Predefined stopping rule**: Run to planned sample size
- **No early stopping**: Test completed as planned (21 days)
- **Balanced traffic split**: 50.2% / 49.8% (minimal imbalance)
- **Clean assignment**: User-level, cookie-based, consistent throughout
- **No external contamination**: No identified overlapping events

All of these indicators suggest the core experimental procedure was executed responsibly.

### Critical Issue: Variance Reduction and Significance Flip

The experiment presents a significant statistical concern that must be addressed before decision-making.

**Raw (unadjusted) result:**
- Control: 34.1%, Test: 34.8%, Delta: +0.7 percentage points
- p-value: 0.091 (not statistically significant at α=0.05)
- Observed effect falls below the pre-planned MDE of +1.0pp

**Adjusted (post-CUPED) result:**
- Control: 34.1%, Test: 34.9%, Delta: +0.8 percentage points
- p-value: 0.028 (statistically significant at α=0.05)

**The Problem:**
The shift from p=0.091 to p=0.028 via variance reduction is dramatic. While CUPED (Controlled Unadjusted Pre-Experiment Data) is a legitimate statistical technique, this particular significance flip raises red flags that must be investigated before the adjusted result can be trusted as the primary decision basis.

## Why This Significance Flip Matters

A large move in p-value via covariate adjustment is not automatically invalid, but it does signal that:

1. **The covariate explained substantial variance**: The fact that adjustment changed the significance threshold implies the pre-experiment engagement variable absorbed a meaningful amount of outcome variance. This is exactly what variance reduction is designed to do, but magnitude matters.

2. **Verification of covariate specification is critical**: The prompt states the covariate is "pre-experiment engagement" but provides insufficient detail:
   - **No metric definition**: What specific engagement metric was used? (clicks, sessions, time-on-site, feature usage, etc.)
   - **No time window specified**: How far back was "pre-experiment" measured? (7 days? 30 days? 90 days?)
   - **No confirmation of non-overlap**: Does the pre-experiment window end clearly before the test start date, or could it partially overlap with the test period?

   Any overlap between the covariate measurement window and the test period introduces **data leakage**, where the covariate is partially measuring the effect of the treatment itself, which invalidates the adjustment.

3. **Covariate contamination risk**: If pre-experiment engagement was measured during a period that partially coincided with test rollout, or if measurement windows were unclear, the covariate could be partially endogenous to the treatment. This would artificially inflate the apparent effect size.

## Major Risks

1. **Post-hoc adjustment without pre-specification** (Severity: Manageable)
   - The team applied CUPED after the test completed, not as part of the initial analysis plan
   - This is a legitimate analysis technique but requires extra scrutiny to avoid p-hacking
   - The team should document whether this was planned before the test ran or added only after observing the raw result

2. **Underspecified covariate definition** (Severity: Manageable to Critical)
   - "Pre-experiment engagement" is too vague to verify
   - Without precise definition and time window, the data leakage risk cannot be assessed
   - Imprecision here makes it impossible to replicate or validate the adjustment

3. **Significance contingent on post-hoc variance reduction** (Severity: Manageable)
   - The original result was non-significant and below the MDE
   - The team is now relying on variance reduction to cross the significance threshold
   - This creates a scenario where the recommendation hinges on a technique choice, not robust evidence

## Reliability Level
**Medium**

The experiment was well-designed and executed procedurally, but the decision hinges on a post-adjustment result that requires additional verification before it can be confidently used.

## Fatal vs Manageable Issues

**No fatal issues detected in the core procedure** (stopping logic, allocation, contamination):
- The test ran to completion with good procedural control
- No early stopping based on performance
- No detected external interference

**Manageable issues that require resolution**:
- Covariate specification must be clearly documented
- Data leakage risk must be ruled out
- Assumption of whether CUPED was pre-specified or post-hoc must be clarified

## Recommendations

**Before shipping, take one of these actions:**

### Option 1 (Preferred): Verify covariate specification and report both results
1. Clearly document the exact definition of "pre-experiment engagement" (metric name, calculation method)
2. Confirm the time window (e.g., "days -30 to -1 relative to experiment start") and verify it does not overlap with the test period
3. Report **both** the raw p-value (0.091) and the adjusted p-value (0.028) in the readout as co-equal evidence
4. Acknowledge that the decision to ship is supported by variance-reduction adjustment, not raw data
5. If the covariate specification is sound and pre-specified, the adjusted result is credible

### Option 2: Accept the raw result and pass
If the pre-planned MDE was +1.0pp and the observed effect was only +0.7pp, the test did not achieve the minimum detectable effect, even before adjustment. Some teams would stop at the raw result and not ship.

### Option 3: Rerun with clear pre-specification
If there is uncertainty about the covariate or whether the adjustment was truly pre-planned, consider running a follow-up test with:
- Covariate clearly pre-specified in the test plan
- Sample size sized for the raw effect (not adjusted)

## Specific Flags for the Team

1. **Flag**: The unadjusted result (p=0.091, +0.7pp) was not statistically significant and fell short of the pre-planned MDE of +1.0pp. This is important context for any decision.

2. **Flag**: A dramatic p-value shift from 0.091 to 0.028 via variance reduction is itself worth scrutiny. The covariate must be verified as sound and non-contaminated.

3. **Flag**: The covariate specification ("pre-experiment engagement") lacks sufficient detail to assess data leakage risk. Precise definition and non-overlapping time window must be confirmed.

4. **Flag**: Variance reduction is a legitimate technique, but when it is the deciding factor in statistical significance, extra verification steps are warranted.

5. **Missing procedural evidence**:
   - Was CUPED pre-specified in the test plan, or added during analysis?
   - What is the precise definition of "pre-experiment engagement"?
   - Over what time window was this covariate measured?
   - Is there any possibility of measurement overlap with the test period?

## Bottom Line

**This experiment has good procedural quality but cannot be confidently shipped based on the post-CUPED result alone without additional verification.**

The team should either:
- Provide clear documentation of the covariate specification and confirm no data leakage, **or**
- Report the raw and adjusted results side-by-side, making clear which one the shipping decision is based on, **or**
- Acknowledge the uncertainty and plan a rerun with clearer pre-specification

The procedure was sound, but the statistical interpretation requires scrutiny before it should drive a shipping decision.
