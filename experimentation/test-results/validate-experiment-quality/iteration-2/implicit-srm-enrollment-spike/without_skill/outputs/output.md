# Experiment Audit: Redesigned In-App Tooltip System

## Summary Recommendation
**DO NOT SHIP — Critical Data Quality Issues**

This experiment has a significant sample ratio mismatch (SRM) that undermines the validity of the results, regardless of the observed p-value.

## Critical Issues Identified

### 1. Sample Ratio Mismatch (SRM)
- Control enrollment: 6,203 users (46.5%)
- Test enrollment: 7,143 users (53.5%)
- Expected: 50/50 split
- Deviation: ~950 additional users in test arm (7.6% imbalance)

This allocation imbalance is material and suggests either a randomization failure or systematic enrollment differences between arms.

### 2. Day 3 Enrollment Anomaly
- Control Day 3: 415 enrollments
- Test Day 3: 1,287 enrollments
- Test Day 3 is ~3.1× the control enrollment on the same day
- Typical daily test enrollment: ~440 users
- Day 3 test enrollment is ~2.9× typical

This spike is a red flag for either a logging error, a traffic spike routed disproportionately to test, or a bucket assignment problem.

### 3. Statistical Result Uncertainty
The observed effect (23.8% vs 22.4%, p=0.031) appears statistically significant, but this conclusion is conditional on:
- Balanced randomization (violated)
- Proper experiment execution (questionable given Day 3 anomaly)
- No measurement or logging artifacts

A p-value of 0.031 with an SRM is not trustworthy. The imbalance could artificially inflate or deflate the effect estimate.

## Risk Assessment
**Risks: FATAL/UNRESOLVED**
- Sample allocation failure indicates a potential systematic issue in how users are being assigned to treatment arms
- The Day 3 spike could indicate a technical problem that occurred mid-experiment
- Results may not reflect true treatment effect

## Required Actions Before Shipping
1. Investigate the root cause of the Day 3 enrollment spike (logging error, traffic routing, randomization bug, etc.)
2. Perform a formal SRM test (chi-square or similar) to quantify the statistical significance of the allocation imbalance
3. If randomization failure is confirmed, consider re-running the experiment with controls in place
4. Validate that the metric definition and logging are consistent across both arms during the anomalous period

## Verdict
**HOLD — Do not proceed to shipping until the SRM and Day 3 anomaly are fully investigated and explained.**
