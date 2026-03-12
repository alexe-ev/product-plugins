# B2B SaaS Navigation Redesign – Experiment Plan (Draft)

## Experiment Overview

We're testing whether collapsing the left sidebar (7 items) into 4 top-level category tabs improves feature discovery and adoption for B2B SaaS users.

## What We Have

- **Treatment:** Top navigation tabs (4 categories) replacing left sidebar (7 items)
- **Control:** Current 7-item left sidebar
- **Expected Impact Direction:** Improved feature adoption, faster navigation, reduced cognitive load

## What's Unresolved (Critical)

1. **Primary Metric** – We need to decide on one clear metric. Candidates include:
   - % of users accessing features outside their primary workflow per session
   - Average feature breadth per user (# of distinct features used per week)
   - Session duration or time-to-task for common workflows
   - Click-through rate to secondary/discovery features

2. **Audience Scope** – Must decide:
   - **All logged-in users** (more statistical power, but existing users are already accustomed to current navigation)
   - **New accounts only** (< 30 days) (cleaner treatment effect, but smaller sample, longer to reach significance)
   - Each choice affects learning curves and contamination risk

3. **Success Threshold** – Not yet defined:
   - What counts as "meaningful improvement"? (5% relative lift? 10%? 15%?)
   - Without this, we can't calculate sample size or power

4. **Sample Size & Duration** – Dependent on above:
   - "2–4 weeks" is a guess without:
     - Baseline metric distribution
     - Minimum detectable effect size
     - Desired statistical power (80%? 90%?)
   - We need: a power analysis once metric & threshold are locked

## Partial Structure

| Component | Status | Notes |
|-----------|--------|-------|
| Treatment | ✅ Defined | 4-tab top nav |
| Control | ✅ Defined | 7-item sidebar |
| Primary Metric | ❌ Unresolved | Candidates listed; need final choice |
| Success Threshold | ❌ Unresolved | Define minimum lift (%) |
| Audience | ❌ Unresolved | All users vs. new only? |
| Sample Size | ❌ Unresolved | Depends on metric + threshold |
| Duration | ❌ Unresolved | 2–4 weeks is preliminary; needs stopping rule |
| Guardrails | ⚠️ Partial | Suggest monitoring: engagement, session time, error rates |

## Why Audience Choice Matters

- **All Users:** Existing users have learned current nav; treatment effect might be diluted by habit. But you get faster significance.
- **New Accounts:** Cleaner learning curve comparison, less confounding. But smaller pool; slower to statistical significance.

## Next Steps

1. Stakeholder alignment on primary metric
2. Define success threshold (minimum % improvement)
3. Decide audience scope
4. Calculate required sample size + duration via power analysis
5. Set explicit stopping rule (e.g., "stop after 4 weeks OR when we reach 10,000 exposures")
