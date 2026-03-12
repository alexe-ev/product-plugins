# Hypothesis Formulation Process - Transcript

## Task Input (Russian)
У нас SaaS для управления проектами. Пользователи жалуются, что им сложно найти нужный проект. Хотим попробовать добавить поиск с фильтрами на главную страницу.

**English Translation:**
We have a SaaS for project management. Users complain that it's hard for them to find the right project. We want to try adding search with filters to the home page.

---

## Step 1: Identify the core problem, opportunity, or assumption

**Core Problem:**
Users struggle to locate projects within the system, indicating a discovery/navigation friction point.

**Proposed Intervention:**
Add search functionality with filters on the home page.

**Type:** Problem-driven opportunity to improve user experience and reduce friction in project discovery.

---

## Step 2: Extract the proposed product change or intervention

**What is changing:**
- Adding a search feature with filtering capabilities
- Location: home/main page of the project management SaaS
- The change is in the navigation/discovery experience

---

## Step 3: Identify the likely target segment

**Available info:**
- "Users complain" → suggests all active users may be affected
- No explicit specification of: new vs. existing users, plan tier, company size, use case

**Most likely target:**
Users who need to locate projects, which could be:
- All users (most inclusive)
- Power users with many projects (most likely to struggle)
- Users with specific project types or team structures

**Decision:** Use "users with project discovery needs" as the primary segment, noting that the actual target (new users, power users, etc.) is unclear.

---

## Step 4: Identify the likely primary metric affected by the change

**Candidate metrics:**
1. **Time-to-project-discovery** - How quickly users find a project
2. **Project-search-success-rate** - Whether users successfully find projects using the new search
3. **User-engagement-with-project-list** - Time spent or interactions with projects after discovery
4. **Task-completion-time** - Time from wanting to access a project to successfully opening it
5. **Activation/re-engagement rate** - Whether easier project discovery improves daily/weekly return

**Most likely primary metric:**
- **Time to project access** or **Project discovery success rate**
- This directly measures whether the new search + filters solve the stated problem

**Alternative secondary metrics:**
- Engagement with projects
- Task completion efficiency
- Feature adoption of search/filters

---

## Step 5: Explain the causal mechanism in plain language

**How this might work:**

The current state: Users scroll through projects or use unclear navigation methods → friction → incomplete/slow project access.

The proposed change: Add search with filters to the home page.

The mechanism:
1. Users can now query for projects by name, team, or other filters
2. Search reduces need to scroll through entire project list
3. Filters let users narrow by relevant criteria quickly
4. Result: Faster, more successful project discovery

**Why this mechanism is plausible:**
- Search is a standard, proven pattern for discovery
- Filters address the complexity of "finding the right project" (suggests multiple attributes matter)
- Home page placement is high-visibility

---

## Step 6: Rewrite into a testable hypothesis

**Candidate hypothesis:**

If we add search with filters to the home page for users needing to locate projects,
we expect time to project access to decrease,
because search functionality reduces navigation friction and allows users to find projects without scrolling.

---

## Step 7: Check for vagueness and missing context

**What is explicitly clear:**
- Product area: project management SaaS
- Intervention: search + filters on home page
- Problem: difficulty finding projects

**What is unclear:**
1. **Segment precision:** Are we targeting all users or a specific cohort?
   - New users onboarding?
   - Power users with 50+ projects?
   - All active users?

2. **Current baseline:** How are projects currently discovered?
   - Sidebar list?
   - Navigation menu?
   - Search already exists elsewhere?

3. **Metric definition:** What does "hard to find" translate to in quantifiable terms?
   - Time spent searching?
   - Success rate of finding the right project?
   - User satisfaction?
   - Feature adoption?

4. **Scope:** Does this apply to all users or specific platforms?
   - Web only?
   - Web + mobile?
   - All interfaces?

5. **Success criteria:** What improvement would make this a win?
   - 10% faster discovery?
   - 50% of users use new search?

---

## Step 8: Check for bundled changes

**Analysis:**
This is ONE core change: adding search + filters to the home page.

The change is bundled, but coherent (search and filters are complementary features addressing the same problem).

**Decision:** Keep as one hypothesis. The search + filters are tightly coupled and represent a single intervention.

---

## Step 9: Do not fabricate quantitative impact

**Current approach:**
No user data provided on current discovery time, user effort, or baseline metrics.

**Decision:** Do NOT assume a specific uplift (e.g., "20% faster search").

Expected direction: Increase in search efficiency / Decrease in discovery time.

This is directional, not quantitative.

---

## Step 10: Expected impact hypothesis assessment

**Can we make a reasonable directional assumption?**

Yes, directionally:
- Search is a proven pattern
- Adding it to a high-visibility location (home page) should improve discoverability
- The bottleneck (finding projects) is well-identified

**Quantitative assumption:**
Not justified without baseline data on current discovery friction.

**Directional assumption:**
Positive impact on discovery speed/success is reasonable.

---

## Context Level Assessment

**Context indicators:**
- Product area: ✓ Clear (project management SaaS)
- Problem: ✓ Clear (hard to find projects)
- Intervention: ✓ Clear (search + filters on home page)
- Target segment: ✗ Unclear (all users? power users? new users?)
- Metric: ⚠ Inferrable but not explicit
- Business goal: ✗ Not stated
- Current baseline: ✗ Not provided
- Expected uplift: ✗ No data

**Conclusion:** LIGHT CONTEXT

The core problem and intervention are clear, but segment definition, metric clarity, and baseline data are missing.

---

## Summary for Output

**Hypothesis statement:**
If we add search with filters to the home page for users needing to locate projects,
we expect project discovery time to decrease,
because search functionality reduces the effort required to find projects compared to manual navigation.

**Target segment:**
Users of the project management SaaS, likely those with multiple projects or frequent project-switching needs (not explicitly confirmed)

**Likely primary metric:**
Time to locate and access a project (or Project discovery success rate if success is binary)

**Expected direction:**
Decrease in discovery time / Increase in discovery success rate

**Why this might work:**
Search is a proven pattern for discovery. Adding it to the home page reduces friction by eliminating the need for users to manually browse or navigate through menus.

**Expected impact hypothesis:**
Not quantified (insufficient baseline data). Directionally positive based on established UX patterns.

**Missing information:**
1. Which user segment is most affected? (new users, power users, all users?)
2. What is the current project discovery method/baseline?
3. How do we measure discovery success? (time, success rate, satisfaction?)
4. Are there guardrails (e.g., search quality, filter relevance)?
5. Is there existing usage data on how users currently find projects?

**Confidence level:**
Provisional

---

## Reasoning Conclusion

This input provides a clear problem and solution but lacks the segment and metric clarity needed for execution-ready confidence. The next step should be to confirm:
- Whether this test applies to all users or a specific cohort
- The baseline discovery experience and current metrics
- The definition of success for this change

With those confirmations, this hypothesis can move to "context-informed" confidence level.
