# EXPERIMENT QUALITY AUDIT

**Quality Verdict:** Limited-confidence audit

**Summary:** While the numerical result appears strong (p=0.0001, +35% relative uplift), critical procedural evidence is missing that would be required to certify this experiment as trustworthy.

**Major Risks Identified:**

1. **Unknown stopping logic** — No information about how or when the experiment was planned to stop. The 6-week duration and strong result raise questions: Was this duration predefined or chosen post-hoc? Did the team monitor results during the test and stop when significance was achieved?

2. **Unknown sample size planning** — No evidence that sample size was calculated in advance. Sample size planning is fundamental to valid inference; without it, we cannot rule out peeking or optional stopping.

3. **Unknown allocation verification** — No confirmation that the control/test split remained balanced throughout the experiment or how traffic assignment was implemented.

4. **Unknown interim monitoring behavior** — The statement "team is very confident this is a real effect" suggests possible interim monitoring. If interim results were reviewed and the experiment was stopped because results looked good, this invalidates classical p-value interpretation.

5. **Unknown contamination assessment** — No information about user-level uniqueness, cross-device behavior, or whether users could be exposed to both variants.

**Reliability Level:** Unknown / Limited confidence

**Fatal vs Manageable Issues:**
- No immediately confirmed fatal flaw, but multiple unresolved risks prevent a strong trust verdict
- If the team stopped the test because interim results looked promising, that would be a fatal issue

**Recommendation:** Treat cautiously

The strong p-value (0.0001) does not substitute for procedural evidence. A strong numerical result can still be unreliable if the procedure was outcome-dependent or inadequately controlled.

**Before shipping, please provide:**
- Was sample size predefined? If so, what was the calculation?
- Was stopping logic predefined? What was the planned endpoint?
- Were interim results monitored during the test?
- If interim monitoring occurred, was action taken based on interim looks (e.g., stopping early)?
- How was traffic allocated between control and test? Was the split verified?
- Could individual users see multiple variants?

**Verdict:** Do not ship until procedural quality is confirmed. Request the missing evidence above before proceeding.
