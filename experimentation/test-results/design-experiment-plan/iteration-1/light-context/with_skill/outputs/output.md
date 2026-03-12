# EXPERIMENT PLAN: Navigation Redesign (Sidebar to Top Tabs)

**Plan status:** Partial planning skeleton — NOT execution-ready. Multiple critical fields remain unresolved and block launch.

---

## Objective

Improve feature adoption and user navigation efficiency by restructuring information architecture.

---

## Hypothesis

If we collapse the 7-item left sidebar into 4 top-level category tabs at the top of the screen for logged-in users, feature adoption should improve because users will experience less visual clutter and faster category access.

---

## Variants

- **Control:** Current 7-item left sidebar layout
- **Test:** New 4-item top-level category tabs

---

## Target audience

**UNRESOLVED** — Audience decision is critical to experiment design

Two options must be decided:
- **All logged-in users:** Larger sample, faster statistical power, but risks contamination from experienced users with established mental models
- **New accounts only (≤30 days):** Smaller sample, longer duration needed, but cleaner signal for onboarding friction reduction and less learning-curve noise

### Why this matters

If you choose all-users, established users may ignore the new tabs initially (learned behavior), diluting the improvement signal. If you choose new-only, you'll need larger time buffer to accumulate sufficient sample size, and adoption improvements may not persist once users mature beyond 30 days.

**Recommendation:** Define audience based on product strategy: Are you optimizing onboarding friction (new-only) or broader information architecture (all-users)?

---

## Metrics

### Primary metric

**UNRESOLVED** — Exact definition needed

Candidates:
- Feature adoption rate (% of users accessing each new category)
- Time to first feature use (days post-login)
- Monthly active feature users (DAU/MAU segmented by category)
- Navigation task completion time (if trackable)

**Decision needed:** What constitutes "meaningful adoption improvement"? Pick one metric that maps directly to business impact.

### Secondary metrics (guardrails)

- Navigation search usage (watch for whether users abandon tabs and search instead)
- Session drop-off rate (ensure the new layout doesn't break existing workflows)
- Page load time (ensure no performance regression)
- Support contact rate related to navigation

---

## Success thresholds

**UNRESOLVED** — Minimum meaningful effect not defined

Current status: "We'd like to detect any meaningful improvement" is too vague for valid experiment design.

**Decision needed:** Define one of the following:
- Minimum % relative uplift (e.g., "adoption must increase by at least 15% relative")
- Minimum absolute uplift (e.g., "adoption rate must rise from 60% to 68%")
- Business outcome threshold (e.g., "feature X usage must increase by 500 MAU")

Without this threshold, you cannot set stopping rules or interpret results reliably.

---

## Sample size and duration

**UNRESOLVED** — No estimates available

**Decision needed:**
- How many users are in your target segment per day/week?
- What statistical power do you need (80%, 90%)?
- Once you define the primary metric and minimum effect size, calculate required sample.
- Estimate how long it takes to reach that sample given your user volume.

Current plan ("2–4 weeks") is a calendar guess, not a statistical commitment.

---

## Stopping logic

**UNRESOLVED** — No fixed stopping rule defined

Current status: Flexible stopping without guardrails is a validity risk (p-hacking, optional stopping bias).

**Options to choose from:**
- **Fixed-horizon:** Run until predefined sample size is reached, then analyze once.
- **Sequential:** Set guardrail thresholds that trigger early shutdown (e.g., "if navigation drop-off exceeds 5%, kill test immediately").
- **Hybrid:** Run for minimum 2 weeks (to capture real usage patterns), then check for statistical significance at weekly checkpoints.

**Recommendation:** Choose fixed-horizon unless you have severe operational risk (e.g., major performance issue or support spike).

---

## Analysis plan (draft)

- Compare primary metric between control and test using appropriate statistical test (t-test for continuous, chi-square for rates).
- Analyze by segment (all-users vs. new-only subgroup, if applicable) to detect heterogeneous effects.
- Monitor guardrails for any adverse signal (drop-off, support load).
- Document any deviations from planned stopping rule.

---

## Decision rules (pending resolution of thresholds)

- **Success outcome:** If primary metric exceeds success threshold AND guardrails remain healthy → Roll out to all logged-in users.
- **Mixed outcome:** If metric improves but threshold not met, OR if guardrails show minor degradation → Iterate on design or run follow-up test.
- **Failure outcome:** If metric flat or declines, OR guardrails show material harm → Reject and return to sidebar layout.

---

## Operational and validity risks

1. **Audience contamination (if all-users):** Existing users with ingrained sidebar habits may not adopt new tabs, even if new users find them better. Signal gets diluted.
2. **Learning curve:** New layout may see initial confusion spike before improvement. Need sufficient duration to observe post-adaptation behavior.
3. **Flexible stopping:** Without fixed end-point, team may be tempted to stop early on favorable early trends (look-ahead bias) or extend if results are neutral.
4. **Mobile/responsive risk:** Confirm how top tabs behave on mobile/tablet — may break on small screens.
5. **Category mapping:** Ensure the 7→4 category consolidation is intuitive. If users can't find expected items, adoption will tank regardless of UI clarity.

---

## Missing fields that block launch readiness

1. **Primary metric exact definition** — activation, adoption, task completion, or time-to-use?
2. **Audience decision** — all logged-in users vs. new accounts ≤30 days?
3. **Minimum meaningful effect** — % uplift, absolute user count, or business outcome threshold?
4. **Sample size and duration estimates** — based on user volume and chosen effect size?
5. **Stopping rule** — fixed-horizon, sequential with guardrails, or hybrid checkpoint?

---

## Next steps before launch

- Align on primary metric and success threshold with stakeholders.
- Decide audience (implications for sample size and duration).
- Calculate sample size and realistic duration.
- Define stopping rule (fixed vs. sequential).
- Confirm mobile layout safety.
- Run category mapping usability check (ensure 7→4 collapse is intuitive).
