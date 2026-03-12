# EXPERIMENT QUALITY ASSESSMENT: Redesigned Checkout Summary Page

## Critical Issue: Post-Hoc Metric Switch Detected

⚠️ **RED FLAG:** The team has engaged in metric switching after observing the pre-planned primary metric failed to reach statistical significance.

### What Happened
- **Planned primary metric:** Checkout completion rate (71.3% → 72.5%, p = 0.18) — NOT statistically significant
- **Post-hoc pivot:** Revenue per session (p = 0.031) — statistically significant
- **Proposed action:** Use the post-hoc finding as the primary basis for a shipping decision

---

## Why This Is Problematic

### Multiple Comparisons & HARKing (Hypothesizing After Results are Known)

When a team observes multiple metrics and selectively reports the one that achieved significance after the planned primary metric failed, this inflates the false positive rate. Here's why:

1. **Uncontrolled statistical testing:** The team implicitly ran multiple hypothesis tests (checkout completion + revenue per session). Without adjusting the significance threshold (e.g., Bonferroni correction), the probability that *at least one* passes p < 0.05 by chance alone is much higher than 5%.

2. **Selection bias:** Reporting the significant result (revenue) and ignoring the null result (checkout completion) is a form of p-hacking—choosing which findings to highlight based on their statistical outcome rather than pre-specified importance.

3. **Plausible story-building:** A $1.40 revenue lift *sounds* meaningful and aligns with business intuition ("revenue matters more"), but this narrative can emerge *from the data* rather than from genuine user behavior change. The post-hoc framing makes it hard to distinguish signal from noise.

---

## Reliability of the Revenue Finding

**The revenue per session result cannot serve as a trustworthy primary basis for shipping because:**

- **Unregistered hypothesis:** Revenue was not the pre-specified primary metric. It was discovered after the main metric failed.
- **Single observation:** We have one p-value (0.031) from one test with no pre-registered stopping rule or sequential testing plan.
- **No multiple comparison correction:** The team did not adjust significance thresholds for the implicit multiple tests.
- **Vulnerable to noise:** The effect ($1.40 per session) could reflect sampling variation, outliers, or data-driven cherry-picking rather than a true causal effect.

---

## Recommendation: Treat as Hypothesis-Generating, Not Confirmatory

**This finding should be:**

1. **Acknowledged** as an interesting post-hoc signal worth investigating
2. **Registered** as the primary metric in a **follow-up experiment** with:
   - Revenue per session pre-specified as the primary outcome
   - A new, predefined sample size and stopping rule
   - Pre-specified success criteria (e.g., p < 0.05, minimum detectable effect)
3. **Not used** as the primary justification for shipping this design now

---

## Quality Risk Classification

**Risk Level: FATAL**

This decision violates fundamental experimental rigor. Shipping based on a post-hoc metric switch introduces substantial false positive risk. The business may invest in a design change that appears beneficial due to selection bias rather than genuine improvement.

### Key Principles Violated
- Pre-registration of primary metrics
- Multiple comparison control
- Distinction between exploratory and confirmatory findings
- Avoiding HARKing (Hypothesizing After Results are Known)

---

## Next Steps

1. **Do not ship** based on the current data
2. **Document** the revenue per session finding as a hypothesis worth testing
3. **Design a follow-up experiment** with revenue per session as the pre-specified primary metric
4. **Run that experiment** with appropriate statistical controls before making a shipping decision
