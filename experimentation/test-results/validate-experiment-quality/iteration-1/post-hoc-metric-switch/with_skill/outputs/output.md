# Experiment Quality Audit: Redesigned Checkout Summary Page

## Quality Verdict
**CONDITIONAL — Procedurally sound with a critical metric-selection issue that undermines the shipping recommendation.**

The procedural setup is strong: predefined sample size, predefined stopping rule, balanced allocation, no interim peeking. However, the team's proposal to use a post-hoc metric switch as the basis for shipping introduces a **fatal reliability risk**.

---

## The Critical Issue: Post-Hoc Metric Switch

### What happened:
1. Planned primary metric (checkout completion rate): +1.2pp, p = 0.18 — **NOT statistically significant**
2. Team then reported an unplanned metric (revenue per session): +$1.40, p = 0.031 — **statistically significant**
3. Team proposes using the post-hoc significant result as the primary basis for the shipping decision.

### Why this is a major problem:

This is a textbook case of **HARKing** (Hypothesizing After Results are Known) combined with **multiple comparisons** without correction:

- The team ran two metrics (or more) and chose to emphasize the one that achieved significance.
- Once the planned metric failed to reach significance, the incentive shifted to finding *any* significant result.
- The original p-value threshold (α = 0.05) was set with one primary metric in mind, not for multiple hypothesis testing.
- If the team measured many metrics post-hoc and reported only the significant one(s), the false-positive risk is substantially inflated.

### False-positive risk inflation:
- Expected false-positive rate under a single pre-registered metric at α = 0.05: ~5%
- Actual false-positive rate when searching across multiple metrics and selecting the "winner": **substantially higher**, potentially 20–40% or more depending on how many metrics were explored.

The observed p = 0.031 for revenue per session may simply reflect noise from repeated testing, not a true effect.

---

## What the Data Actually Show

**Planned metric (checkout completion):** The redesign did NOT improve the planned outcome. This is the direct, pre-registered measure of the hypothesis.

**Unplanned metric (revenue per session):** A statistically significant difference was found, but this finding was **generated after observing that the primary metric failed**, which triggers selection bias and multiple-comparison concerns.

---

## Risk Classification

| Risk | Severity | Explanation |
|------|----------|-------------|
| Post-hoc metric switch | **FATAL** | Planned metric failed; team switched to reporting an unplanned metric after observing results. This inflates false-positive risk and undermines the validity of the p-value. |
| Multiple comparisons without correction | **FATAL** | The team appears to have tested multiple metrics and reported the significant one without adjusting the significance threshold. |
| Business rationalization | **Manageable** | Revenue is indeed commercially important, but this does not justify using a post-hoc, uncontrolled finding as the primary basis for a shipping decision. |

---

## Procedural Strengths (Noted)

The experiment was well-designed in terms of:
- Sample size predefined and adequate
- Stopping rule predefined and followed
- Traffic allocation well-balanced (50.1% / 49.9%)
- No interim peeking or early stopping
- User-level assignment
- No overlapping external events

These strengths support trustworthiness for the **planned metric**, but cannot rescue a post-hoc metric switch from selection bias.

---

## Recommendation

**DO NOT ship based on the revenue per session finding.**

Instead:

1. **Treat the revenue per session result as hypothesis-generating.** It is a candidate finding, not a validated primary outcome.

2. **Rerun the experiment** with revenue per session as a pre-registered primary metric (or co-primary with checkout completion). Design and power the test to detect a realistic effect size on revenue.

3. **If you ship now**, you would be relying on a post-hoc, uncontrolled finding with inflated false-positive risk. This violates sound experimentation practice.

4. **Acknowledge the failed planned metric.** The redesign did not move checkout completion. That is the actual result. Revenue per session may be real, but it cannot serve as a substitute for a valid primary finding without a proper follow-up test.

---

## Reliability Level

**Procedurally strong, but invalid as a basis for the proposed decision.**

The experiment procedure itself was sound. The issue is *how the result is being interpreted*: the team is using an unplanned, post-hoc finding in place of the failed primary metric.

---

## Missing Procedural Evidence

- How many total metrics were measured or analyzed post-hoc?
- Was revenue per session measured and recorded as part of the original test design, or was it discovered after the fact?
- Did the team look at any other secondary metrics?

If revenue per session was among pre-specified secondary metrics with a clear hierarchical or corrected significance threshold, the risk profile improves. Please clarify.
