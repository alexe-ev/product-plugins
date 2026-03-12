# Experiment Hypothesis: Project Discovery Search on Home Page

## Hypothesis Statement

If we add search with filters to the home page for users needing to locate projects,
we expect project discovery time to decrease,
because search functionality reduces the effort required to find projects compared to manual navigation.

---

## Target Segment

**Primary target:** Users of the project management SaaS who search for projects

**Specificity level:** Low confidence
- Most likely includes users with multiple projects or frequent project-switching needs
- Unclear whether this applies to:
  - All active users
  - New users during onboarding
  - Power users with large project portfolios
  - Users at specific plan tiers

**Recommendation:** Confirm whether the test applies to all users or a specific cohort before proceeding.

---

## Likely Primary Metric

**Primary metric:** Time to project discovery / Project access time
- How long it takes a user to locate and open a specific project from the home page

**Alternative formulation:** Project discovery success rate
- If discovery is binary (user finds project or does not), this measures the percentage of discovery attempts that succeed

**Why this metric:**
The stated problem is that users find it "hard to find" projects, suggesting speed and/or success is the key outcome to measure.

---

## Expected Direction of Impact

**Expected impact:** Decrease in discovery time OR increase in discovery success rate

Direction is clearly **positive** because search is a well-established UX pattern that reduces friction.

---

## Why This Might Work

1. **Proven pattern:** Search is a standard, effective discovery mechanism across products with large catalogs or lists.

2. **Reduces friction:** The current state requires users to navigate menus or scroll through lists. Search eliminates this manual work.

3. **Filters add precision:** The addition of filters suggests that projects have multiple attributes (team, status, type, etc.). Filters let users narrow results quickly rather than scanning the full list.

4. **High visibility:** Placing the search on the home page ensures users see it when they need it most (when looking for a project).

5. **Addresses stated pain:** Users explicitly complain about difficulty finding projects, indicating this is a real friction point.

---

## Expected Impact Hypothesis

**Quantitative estimate:** Not defined yet

**Reason:** No baseline data provided on current discovery time, success rates, or user effort.

**Directional confidence:** Moderate to high
- Search improving discovery is a well-established pattern
- However, the magnitude of impact depends on: current discovery method, project list size, filter quality, and segment

**To move forward, we need:**
- Baseline measurement of current project discovery time/success rate
- Data on how often users search for projects
- Understanding of what makes projects "hard to find" (too many projects? unclear naming? lack of categorization?)

---

## Missing Information

Before moving to validation or metric definition, confirm:

1. **Segment clarity**
   - Does this apply to all users or a specific cohort?
   - Are new users included, or only existing users?
   - Are power users (with many projects) more affected?

2. **Current state**
   - How do users currently discover projects? (sidebar, menu, existing search elsewhere?)
   - What is the current baseline metric? (e.g., average discovery time, success rate)
   - Is search already available in other parts of the product?

3. **Metric definition**
   - How should "time to discovery" be measured? (from home page load? from click?)
   - If success rate: how do we define a successful discovery?
   - Are there secondary metrics? (e.g., feature adoption, user satisfaction, task completion time)

4. **Scope and constraints**
   - Does this apply to all platforms (web, mobile) or web only?
   - Are there any guardrails or guardrail metrics? (e.g., search quality threshold, filter relevance)

5. **Business context**
   - Is the goal to improve user satisfaction, reduce support tickets, or increase engagement?
   - Are there competing priorities or constraints on where to add this feature?

---

## Confidence Level of Hypothesis Framing

**Confidence: PROVISIONAL**

**Reasoning:**
- The core problem and intervention are clear
- The causal mechanism is sound (search improves discovery)
- However, the segment is not precisely defined, and the baseline metric is unknown
- The hypothesis is testable, but would benefit from more context before designing the experiment

**Path to higher confidence:**
1. Confirm which segment(s) to test with
2. Define the baseline for project discovery (current time/success rate)
3. Clarify the primary success metric
4. Identify any guardrails or secondary metrics
→ Once these are confirmed, this hypothesis can move to "context-informed" or "execution-ready candidate" confidence level

---

## Downstream Handoff

This hypothesis is ready for:
- **validate-hypothesis-quality:** To stress-test the assumption that search improves discovery
- **define-success-metrics:** To translate "discovery time" into a precise, measurable metric
- **design-experiment-plan:** To define the control and treatment groups, rollout strategy, and duration

**Before handoff to these skills, resolve:**
1. Segment definition (who are we testing with?)
2. Metric baseline (what is the current discovery time/rate?)
3. Any platform-specific constraints or guardrails

---

## Summary

**Problem:** Users struggle to find projects in the project management SaaS.

**Solution:** Add search with filters to the home page.

**Hypothesis:** Search + filters on the home page will reduce project discovery time because search is a proven pattern that eliminates manual navigation friction.

**Status:** Provisional - clear problem and solution, but segment and metric definitions need confirmation before proceeding to experiment design.
