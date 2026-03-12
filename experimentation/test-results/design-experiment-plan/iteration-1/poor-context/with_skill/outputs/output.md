**Planning Skeleton: Experiment Design for Design Preference Test**

**Objective:**
To be defined — need clarity on what business outcome (conversion, engagement, retention, satisfaction) is tied to design preference.

**Hypothesis:**
To be clarified. Current assumption: If we deploy the new design, users will prefer it, resulting in [outcome]. But we need:
- What specifically changes about the design?
- Why do we believe it will be preferred?
- What is the mechanism that links preference to business impact?

**Control:**
Current design (to be confirmed)

**Test:**
New design (to be confirmed in detail)

**Target audience:**
To be defined. Which users are affected?
- All users or a segment (e.g., new users, mobile users, certain regions)?
- Which product area or funnel step?

**Primary metric:**
To be defined. "Prefer" is subjective — what is the measurable outcome?
- Design completion rate?
- Task success rate?
- Time-on-task?
- Satisfaction score?
- Conversion rate?
- Engagement?

**Secondary metrics:**
To be defined

**Guardrails:**
To be defined

---

**CRITICAL VALIDITY RISK: Early stopping**
You mentioned "stop the test early if we see good results." This is a significant statistical validity threat:
- **Optional stopping / peeking**: Stopping when results "look good" inflates false positive rates and breaks statistical power assumptions
- **P-hacking**: Early stopping allows you to select favorable moments in the test window, compromising the validity of your result
- **Recommendation**: Commit to a fixed sample size and test duration before launching. If you must stop early, reserve that decision for guardrail violations only, and adjust your significance threshold accordingly.

---

**Minimum context required before this becomes execution-ready:**

1. **What change is being tested?** (specific design details, components, flows affected)
2. **Which users are affected?** (target segment definition)
3. **What is the primary metric?** (what specific behavior or outcome reflects success?)
4. **What constitutes "good results"?** (numeric success threshold, e.g., +10% relative uplift)
5. **What is the stopping logic?** (fixed duration and sample size, or specific guardrail thresholds?)
6. **How long do you expect the test to run?** (if not pre-estimated, needed for power calculation)

---

**Plan status:**
Planning scaffold only — not execution-ready. Core decisions on metric definition, success criteria, and valid stopping logic must be defined first.
