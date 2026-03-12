# Experiment Hypothesis Formulation Output

## Original Input
"Конверсия падает, надо что-то делать. Думаем поменять цвет кнопки. Это должно поднять конверсию на 30%."

Translation: "Conversion is falling, something needs to be done. We're thinking of changing the button color. This should raise conversion by 30%."

---

## Analysis & Context Assessment

### What is known:
- A conversion metric is declining
- The proposed intervention is changing a button's color
- The team expects a substantial impact (30% uplift)

### What is assumed or missing:
- Which product area or funnel stage is affected
- Which button specifically
- Which user segment will see this change
- What conversion event is the target
- Why the team believes button color will affect conversion
- The basis for the 30% uplift assumption

### Context level:
**CONTEXT-POOR** — Core product context, specific button location, target segment, and funnel stage are not defined. The 30% claim lacks any evidence basis.

---

## Provisional Hypothesis

**If we change the color of a conversion-driving button for all users,**
**we expect the conversion rate to increase,**
**because button color may improve visual contrast, clarity, or call-to-action prominence and reduce friction in a conversion funnel.**

---

## Hypothesis Details

### Target segment:
Unconfirmed. Likely: all users on the affected funnel, but unknown whether this is:
- New vs. returning users
- Mobile, web, or both
- A specific geographic or demographic segment
- Users at a specific funnel stage

### Likely primary metric:
Conversion rate (but definition is unclear):
- Conversion to what end state? (purchase, signup, form submission, button click?)
- Over what time period? (session, 24h, 30d?)
- By what denominator? (visitors, sessions, users?)

### Expected direction of impact:
Increase (in conversion rate)

### Why this might work:
Button color can influence conversion through several mechanisms:
- **Visual contrast**: A higher-contrast color may draw attention and increase click-through
- **Call-to-action clarity**: A distinctive color may communicate that the button is actionable
- **Psychological association**: Certain colors (e.g., green, orange) are culturally associated with positive actions or trust in some contexts
- **Consistency**: If the new color better aligns with brand or design language, it may feel less jarring

### Why this might NOT work:
- Button color is a surface-level UI change; if conversion is falling due to product, pricing, messaging, or targeting issues, color alone will not fix it
- Without knowing the current color, baseline, and user expectations, the change could reduce contrast or confusion instead of improving it
- Other variables in the funnel may be the real bottleneck

---

## Expected Impact Hypothesis

**NOT DEFINED — Impact assumption is unsupported.**

The user claims a 30% uplift is expected. However:
- No prior test results are cited
- No industry benchmarks are provided
- No documented rationale (e.g., "A/B tests in our product have shown X% uplift from color changes in similar contexts") is given
- This appears to be an intuitive guess rather than an evidence-based prediction

**Action**: Flag this number as needing validation. Do not use 30% in the experiment design or success criteria. Instead, proceed to hypothesis validation and define realistic guardrails and minimal uplift thresholds based on statistical power and business context.

---

## Missing Information (Critical before moving to validation)

1. **Which button?** Name, location, and funnel stage (e.g., "Add to Cart button on product detail page", "Subscribe button on pricing page")
2. **Current button color** and **proposed button color** (and rationale for the choice)
3. **Which conversion metric?** Define the event, numerator, denominator, and measurement window
4. **Target segment?** Are all users in scope, or a specific cohort (new users, returning, country, device)?
5. **Baseline conversion rate?** What is the current performance, and how much is it declining?
6. **Why do you believe button color is the issue?** Has user research, heatmaps, session recordings, or A/B testing in other products suggested this?
7. **Have other factors been ruled out?** (e.g., product quality, pricing, messaging, traffic quality, seasonal effects)
8. **What is your minimum meaningful uplift?** Is 30% realistic, or should guardrails be narrower?

---

## Suggested Next Steps (Discovery)

Before moving to hypothesis validation or experiment design, resolve at least 2–3 of the critical missing items:

1. **Product area clarification**: Ask the team which button, page, and funnel stage they're referring to
2. **Baseline metrics**: Pull current conversion rate, traffic, and trend data to confirm the decline and quantify its magnitude
3. **Change rationale**: Ask why the team believes color is the lever (run a 5-minute user research session or review session recordings if available)
4. **Uplift expectation check**: Challenge the 30% assumption with the team; clarify whether it's based on prior tests, competitor benchmarks, or intuition
5. **Segment scope**: Confirm whether this test applies to all users or a subset

---

## Confidence Level of Hypothesis Framing

**PROVISIONAL**

- The core product area (which button, funnel stage) is unconfirmed
- The target segment is inferred but not explicitly defined
- The primary metric definition is incomplete
- The 30% impact assumption is unsupported and should not be treated as a success threshold
- The causal mechanism is plausible but not validated

**Status for handoff**: This hypothesis can move to the next phase (hypothesis validation) once at least 3 of the 8 missing information items are resolved. It is not yet ready for experiment design or sample size calculation.

---

## Downstream Readiness

**Recommend proceeding to**:
- **validate-hypothesis-quality** (once missing context is resolved)
- **define-success-metrics** (once the button, funnel stage, and baseline are confirmed)

**NOT yet ready for**:
- design-experiment-plan (critical context is missing)
- sample size or duration estimation (no validated success metric or impact threshold)
