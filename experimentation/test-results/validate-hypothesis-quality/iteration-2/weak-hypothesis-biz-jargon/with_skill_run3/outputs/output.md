# Hypothesis Validation: Onboarding UX Improvement

## Input
**Hypothesis (original):**
Улучшение UX онбординга повысит активацию новых пользователей.

(English translation: Improving onboarding UX will increase activation of new users.)

---

## Verdict
**Weak**

---

## Main weaknesses

1. **"Улучшение UX онбординга" (Improving onboarding UX) is too vague** — No specific change is described. "UX improvement" could mean anything from visual polish to workflow restructuring to information architecture changes. Without naming the specific intervention (e.g., "reduce form fields," "add progress indicators," "simplify payment flow"), there is no way to isolate the intervention or replicate it in variant design.

2. **"Активацию" (activation) is undefined** — The term "activation" is business jargon that varies widely across products:
   - Does it mean first successful login after signup?
   - First completed action (purchase, post, invite, etc.)?
   - Reaching a specific feature threshold?
   - Returning 7 days after signup?

   Without a precise metric definition, success is unmeasurable.

3. **No target segment is bounded** — "New users" is broad and unqualified:
   - All new users or a specific cohort (e.g., first-time users from organic, paid, or referral)?
   - Mobile-only, web-only, or cross-platform?
   - Geographic, language, or device constraints?

   Different segments may respond very differently to onboarding changes.

4. **No expected effect size or threshold is defined** — There is no claim about how much activation should increase. Without a minimum meaningful effect, you cannot distinguish a true improvement from noise or observer bias.

5. **Causal mechanism is implicit, not stated** — The hypothesis assumes that "UX improvement" will reduce friction or confusion, but the exact causal logic is not articulated. What friction are you removing? What barrier does the onboarding currently present?

6. **No way to objectively evaluate success** — Because the change and metric are both vague, there is no clear pass/fail criterion.

---

## Improved version

**If we streamline the signup form for new users by reducing required fields from 8 to 3 (name, email, password only),**

**we expect the activation rate (first app launch within 7 days of signup) to increase by at least 8% relative,**

**because shorter forms reduce signup friction and abandonment, allowing more new users to proceed to their first in-app session.**

---

## Missing information

- **Exact metric definition:** What event or threshold defines "activation" in your product? (e.g., first login, first action, returning user retention day 1, day 7, etc.)
- **Target segment boundaries:** Are you optimizing for all new signups, or a specific cohort (by channel, device, region, or persona)?
- **Product context:** What does your current onboarding flow look like? What are the current activation and abandonment rates?
- **Business threshold:** What uplift in activation is worth the engineering effort? (5%, 10%, 15%?)
- **Guardrails or risks:** Are there data fields you need to collect that the streamlined form would remove?

---

## Readiness statement

**This hypothesis is NOT ready for experiment design.** It requires a specific description of the UX change, a measurable and precisely defined activation metric, a bounded target segment, and an expected effect threshold before it can advance. Currently, it is valid for exploration only — the direction is sound (onboarding friction likely affects activation), but the execution details are too vague to design a controlled test.

---

## Next steps

1. **Define the metric:** Specify your activation definition in precise, measurable terms.
2. **Name the change:** Describe exactly what UX element or flow you will modify.
3. **Bound the segment:** Clarify which new users will see the change.
4. **Set an effect threshold:** State the minimum improvement you consider meaningful.
5. **Resubmit to validate-hypothesis-quality** with this context added.

Once these are in place, the hypothesis will be ready to hand off to **define-success-metrics** and **estimate-sample-size**.
