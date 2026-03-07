# Reference: Estimate Sample Size

## Why this reference exists

This skill is calculation-aware.

Its job is not to produce decorative numbers.
Its job is to estimate the sample required for a defensible experiment and translate that into a realistic duration estimate when enough inputs are available.

This reference defines:
- required inputs
- calculation assumptions
- context collection logic
- invalid-use conditions
- output interpretation rules

---

## Core principle

Do not estimate sample size from vague intent alone.

Sample size estimation becomes meaningful only when the experiment has:
- a primary metric
- a baseline value
- a minimum detectable effect or minimum meaningful effect
- a significance/confidence level
- a desired power

If duration is requested, the skill also needs:
- eligible traffic, not total product traffic

---

## Context model for this skill

For this skill, context does not mainly mean product storytelling.
It means computational completeness.

### Context-complete
All mandatory inputs are available.

In this state the skill may:
- estimate sample size per variant
- estimate total sample size
- estimate test duration
- comment on feasibility

### Context-partial
Some mandatory inputs are missing.

In this state the skill should:
- estimate only what is defensible
- explicitly list missing assumptions
- avoid fake precision
- stop at setup guidance if calculation would be misleading

### Context-insufficient
The user wants a sample estimate but key inputs are missing.

In this state the skill should:
- not pretend to calculate a meaningful answer
- switch to checklist mode
- explain what inputs are required before estimation

---

## Mandatory inputs

Minimum required inputs for basic sample size estimation:
- metric type
- baseline metric value
- minimum detectable effect or minimum meaningful effect
- significance level or confidence level
- statistical power

Additional required input if duration is requested:
- eligible traffic per period

---

## Why eligible traffic matters

Duration must be estimated from the traffic that can actually enter the test.

Do not use:
- total site traffic
- total app traffic
- total account base

Use:
- the number of users who actually reach the tested step
- the segment that is truly eligible for assignment

If only part of the total audience can enter the experiment, duration must be based on that subset.

---

## Core variables for simple rate experiments

For simple conversion-style experiments, define:

- `p1` = baseline conversion rate
- `p2` = target conversion rate implied by the desired effect
- `n` = required sample size per group

Example logic:
- baseline conversion = 3.2%
- desired absolute uplift = 0.3 percentage points
- target conversion = 3.5%

---

## Calculation logic by metric type

### 1. Conversion / rate metrics
This is the cleanest case.

Use:
- baseline conversion
- target conversion implied by MDE
- chosen significance level
- chosen power

Typical outputs:
- sample size per group
- total sample size
- estimated duration if eligible traffic is known

### 2. Continuous metrics
Examples:
- average revenue per user
- time spent
- average session length

These require dispersion assumptions.
If standard deviation or variance is missing, the estimate is weaker.

In such cases the skill should:
- say the estimate is rough
- ask for standard deviation or historical variance if available
- avoid pretending the answer is exact

### 3. Revenue-like or skewed metrics
These are often noisy and non-normal.

The skill should:
- use extra caution
- avoid oversimplifying
- warn that variance assumptions strongly affect reliability

---

## Duration estimation logic

Use the following idea:

`estimated duration = total required eligible sample / eligible traffic per period`

This estimate must be treated as directional, not guaranteed.

Always check for:
- weekly traffic cycles
- seasonality
- acquisition source mix changes
- launch windows
- campaign periods
- delayed exposure or delayed conversion

If the test must run across unstable periods, say so explicitly.

---

## How to handle missing MDE

Do not guess a fake MDE and move on as if everything is fine.

If MDE is missing:
- explain why it matters
- say sample size cannot be estimated meaningfully without it
- optionally offer scenario-based ranges only if clearly labeled as scenarios

Acceptable fallback:
- “If the team wants to detect a 3% relative uplift, sample size would be X. If the team wants to detect a 7% relative uplift, sample size would be Y.”

Not acceptable:
- silently choosing an arbitrary MDE as if it were fact

---

## How to handle missing significance or power

If the user does not specify them, the skill may use conventional defaults, but it must say so explicitly.

It should not hide defaults.

Good pattern:
- “Using a conventional 95% confidence level and 80% power, the estimated sample size is ...”

Bad pattern:
- returning a number with no explanation of assumptions

---

## Feasibility rules

The skill should comment on feasibility, not just arithmetic.

Useful feasibility checks:
- Is the required sample so large that the test would take too long?
- Is the expected duration too long for the business cadence?
- Is the minimum detectable effect unrealistically small relative to available traffic?
- Is the eligible segment too narrow for a practical experiment?

If feasibility is poor, the skill should say so directly.

---

## Invalid-use conditions

Treat the estimate as incomplete, unreliable, or not ready if:
- baseline is missing
- MDE is missing
- significance/confidence is missing and no explicit default is stated
- power is missing and no explicit default is stated
- eligible traffic is unknown while duration is requested
- the metric is continuous but no variance assumption is available
- the audience used for duration is not actually eligible traffic

---

## Output expectations

A good output should include:
- sample size per group
- total sample size
- estimated duration if possible
- all inputs used
- all assumptions used
- missing inputs if any
- feasibility note
- caveats that materially affect trust

---

## Behavioral rule under incomplete context

If the setup is incomplete, the skill should be useful without hallucinating precision.

That means:
- checklist mode is acceptable
- scenario mode is acceptable when explicitly labeled
- fake precision is not acceptable

---

## Relationship to the experimentation workflow

This skill should usually come after:
- hypothesis framing
- metric definition
- minimum meaningful effect definition

It should not be treated as the place where business importance is invented from scratch.

That work belongs upstream.
