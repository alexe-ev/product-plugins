# Hypothesis Validation Output

## Input
Hypothesis (Original):
Нужно провалидировать: улучшение UX онбординга повысит активацию новых пользователей.

Hypothesis (English translation):
Improving UX onboarding will increase activation of new users.

---

## Analysis

### Instruction 1: Check for specific change
**Finding**: The change is vague.
- "Улучшение UX онбординга" (improving UX onboarding) is not specific about what aspect of UX is being improved
- No concrete change is described (e.g., simplified form, reduced steps, better guidance, visual redesign)

### Instruction 2: Check for measurable outcome
**Finding**: Outcome is partially vague.
- "Активацию новых пользователей" (activation of new users) is business jargon that could mean many things
- "Activation" is not a standard metrics term; it could mean: first login, first feature usage, account confirmation, completing a task, spending money, etc.
- Without clarity on what "activation" means in your product, success cannot be measured objectively

### Instruction 3: Check target segment clarity
**Finding**: Segment is somewhat clear.
- "Новые пользователи" (new users) is a reasonable segment definition
- However, no distinction is made: all new users? Web only? Mobile? First signup within 24 hours? First visit?

### Instruction 4: Check for plausible causal mechanism
**Finding**: Mechanism is vague but plausible.
- The causal logic exists: better UX → lower friction → higher engagement/completion
- However, it's stated implicitly, not explicitly
- No explanation for *why* the onboarding UX change should work

### Instruction 5: Check if success can be evaluated objectively
**Finding**: Cannot be evaluated objectively in current form.
- "Улучшение" (improvement) is subjective
- "Активация" (activation) is undefined
- No success threshold or expected effect magnitude

### Instruction 6: Check for mixed changes
**Finding**: Single hypothesis, but too broad.
- The hypothesis combines a vague change ("improve UX") across an entire flow (onboarding)
- It would be stronger if focused on a specific UX problem and a specific activation metric

### Instruction 7: Check for expected effect magnitude
**Finding**: Not defined.
- No minimum meaningful effect is stated
- No direction (increase, decrease, shift) is quantified

### Instruction 8: Classify hypothesis state
**Verdict**: **Weak**

The hypothesis contains business jargon and lacks the specificity needed for experiment design. It is not invalid (there is a plausible direction), but it cannot guide experiment design without further refinement.

---

## Main Weaknesses

1. **Vague change description**: "Улучшение UX онбординга" (improving UX onboarding) is too abstract. It does not specify what is being improved (form fields, visual design, copy, flow steps, etc.)

2. **Undefined metric**: "Активация новых пользователей" (activation of new users) is business jargon that doesn't translate to a measurable event without context. Activation in product means different things to different teams.

3. **No target segment clarity**: While "new users" is mentioned, the exact cohort is undefined (web vs. mobile? timeframe? geography?).

4. **No explicit causal mechanism**: The connection between the change and outcome is implied but not stated. Why specifically would this UX change drive activation?

5. **No effect threshold**: There is no statement of what constitutes success (e.g., "at least 10% relative increase" or "move from 30% to 35%").

6. **Subjective success criteria**: "Улучшение" (improvement) is subjective. Improvement to whom? By what measure?

---

## Improved Version

**Stronger hypothesis (conditional on onboarding context)**:

If we reduce the number of required fields in the email signup form and add inline validation during onboarding for new web users,
we expect the proportion of new users who complete their first in-app action (e.g., create a document, send a message, or verify email) within 24 hours to increase by at least 8% relative,
because removing friction points and providing clearer guidance should reduce abandonment in the critical early moments.

**Alternative improved hypothesis (if activation means something different in your product)**:

If we simplify the onboarding flow by removing the optional step and replacing it with contextual prompts in the product for new mobile users,
we expect the daily active user rate among cohort-day-1 new users to increase from [baseline] to [baseline + threshold],
because reducing initial friction allows users to experience core value faster.

---

## Missing Information

To move this hypothesis from "weak" to "valid for experiment design," you need to provide:

1. **Specific UX change**: Which part of onboarding? Form reduction? Flow simplification? Copy changes? Visual redesign? Guided onboarding tour?

2. **Activation metric definition**: In your product, what constitutes "activation"? Examples:
   - Completed email verification
   - First feature action (document created, message sent, etc.)
   - Set profile picture
   - Invited a collaborator
   - Spent X minutes in the product
   - Returned on day 2

3. **Target segment precision**:
   - New users only? or users in first N hours/days?
   - Web, mobile, or both?
   - Any geographic or language restrictions?
   - Enterprise vs. consumer?

4. **Minimum meaningful effect**: What is the baseline activation rate? What is the minimum acceptable uplift (absolute or relative)?

5. **Measurement window**: Over how many days post-signup will you measure activation? (e.g., within 24 hours, within 7 days?)

6. **Causal explanation**: Why do you believe this specific UX change will improve activation? Is there user research, analytics, or qualitative feedback supporting this?

---

## Readiness for Next Step

**Readiness State**: Valid for exploration, **not yet valid for experiment design**

This hypothesis is ready to guide a product discussion or scoping conversation, but it cannot be handed off to the experiment design phase without clarification.

---

## Context Gaps Blocking the Next Step

Critical blockers to experiment readiness:

1. **Metric definition**: Cannot pass to `define-success-metrics` skill without knowing what "activation" means in your product vocabulary
2. **Change specification**: Cannot design experiment without knowing exactly what UX change will be tested
3. **Segment definition**: Cannot estimate sample size without knowing the exact cohort (web/mobile? timeframe?)
4. **Effect threshold**: Cannot estimate required sample size or statistical power without baseline and expected uplift
5. **Product context**: No information about current onboarding funnel, baseline activation rate, or why this change is prioritized

---

## Recommendations

**Next steps:**

1. **Align on activation definition**: Work with product and analytics teams to define what "activation" means in your system
2. **Identify the UX problem**: Which specific onboarding friction point are you addressing? (e.g., form abandonment, confusion about next steps, unclear value proposition)
3. **Define the change precisely**: What will the new onboarding look like? Write it out or sketch it
4. **Set success threshold**: What baseline activation rate exists today? What uplift would be meaningful? (e.g., from 45% to 50%, or +10% relative)
5. **Identify platform/segment**: Is this for web, mobile, or both? All new users or a specific cohort?

Once these gaps are filled, re-run this validation and move forward to experiment design.
