# Experiment Quality Audit: Onboarding Email Sequence

## Overall Assessment
**UNTRUSTWORTHY — Caution Required**

## Critical Issues Identified

### 1. Flexible Stopping (High Risk)
The experiment was extended from 21 to 25 days because "results weren't conclusive enough at the 3-week mark." This is a clear case of flexible stopping or outcome-dependent stopping, a form of p-hacking that fundamentally compromises statistical validity.

**Why this matters:**
- The team observed interim results and made a judgment call to extend the test window
- The stopping decision was predicated on observing insufficient clarity, not a pre-specified rule
- This practice inflates false positive rates and invalidates standard statistical inference
- Even with careful monitoring, continuing to run the test based on interim observations violates pre-commitment principles

### 2. Distinction Between Passive Monitoring and Acting on Results
- **Acceptable:** Daily monitoring dashboards (passive surveillance)
- **Problematic:** Extending the test window based on observed interim results

The core violation is that the team *acted* on interim observations by choosing to extend. Standard statistical guarantees depend on stopping rules being set before you look at the data.

### 3. What's Actually Right
- Sample size is solid (12,000 per group)
- Traffic split is well-balanced (49.7% control / 50.3% test)
- No external confounds during the test window
- Metric precisely matches the hypothesis (14-day activation rate)
- User-level assignment is consistent throughout

## Recommendation: Treat Results Cautiously

**Do NOT:**
- Treat final results as having your planned statistical power
- Accept reported p-values or confidence intervals as calibrated
- Make high-stakes decisions based solely on these results

**Appropriate Next Steps:**
- If the effect size is very large, it may still be directionally correct
- Consider this a preliminary or exploratory finding
- Plan a confirmatory follow-up experiment with pre-committed stopping rules
- Document the result but flag it as lower-confidence than originally intended

**For Future Experiments:**
- Pre-commit all stopping rules before the experiment launches (e.g., "Stop at day 21" or "Stop when we reach 50,000 total conversions")
- Separate monitoring (looking at dashboards) from decision-making (choosing when to stop)
- If you genuinely need sequential analysis, use proper sequential testing methods with adjusted significance levels
- Never extend a test based on observed lack of clarity — this is outcome-dependent stopping
