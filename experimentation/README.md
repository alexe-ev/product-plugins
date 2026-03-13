# Experimentation

This section contains skills for product experiments and A/B testing.

The goal here is simple: help an agent move from a rough idea or product problem to a well-structured experiment, then to a trustworthy interpretation of results, and finally to a practical decision.

This is not a statistics textbook and not a dump of random prompts.  
It is a working library of reusable skills for experimentation.

---

## What’s inside

This domain covers the full experiment flow:

```text
idea / problem / observation
    ↓
hypothesis
    ↓
hypothesis validation
    ↓
success metrics
    ↓
sample size and duration
    ↓
experiment plan
    ↓
result analysis
    ↓
quality validation
    ↓
decision
```

Each step is split into a separate skill so the agent can use them independently or combine them when needed.

⸻

Why the skills are split

Running experiments involves several different jobs:
	•	turning vague ideas into hypotheses
	•	checking whether the hypothesis is actually testable
	•	choosing the right metrics
	•	estimating sample size
	•	designing the test
	•	interpreting results
	•	checking whether the test itself was trustworthy
	•	deciding what to do next

Putting all of that into one giant skill would make it harder to reuse, harder to maintain, and easier to misuse.

So this domain uses smaller skills that work well on their own and also connect to each other.

⸻

Skills in this domain

1. formulate-experiment-hypothesis

Use this when there is an idea, observation, or product problem, but no proper hypothesis yet.

What it does:
	•	turns rough thinking into a testable hypothesis
	•	identifies likely segment and likely primary metric
	•	makes missing context explicit

⸻

2. validate-hypothesis-quality

Use this when a draft hypothesis already exists and needs to be checked.

What it does:
	•	checks whether the hypothesis is specific enough
	•	checks whether it is measurable and testable
	•	distinguishes between “good enough for exploration” and “good enough for experiment design”

⸻

3. define-success-metrics

Use this when the hypothesis exists, but success is still vague.

What it does:
	•	defines the primary metric
	•	proposes secondary metrics and guardrails
	•	helps define success threshold, neutral zone, and failure logic

⸻

4. estimate-sample-size

Use this when the team needs to know how much traffic is required and how long the test may need to run.

What it does:
	•	estimates sample size
	•	estimates duration from eligible traffic
	•	flags missing or weak assumptions

This is a calculation-aware skill, so it also has a REFERENCE.md.

⸻

5. design-experiment-plan

Use this when the team is ready to turn the hypothesis into a real test plan.

What it does:
	•	builds the experiment brief
	•	defines variants, audience, metrics, thresholds, and stopping logic
	•	shows what is still missing before launch

⸻

6. analyze-experiment-results

Use this when the experiment is already complete and results need interpretation.

What it does:
	•	compares control and variant
	•	reports uplift and uncertainty
	•	separates observed effect from practical significance
	•	keeps guardrails visible

This is a calculation-aware skill, so it also has a REFERENCE.md.

⸻

7. validate-experiment-quality

Use this when the numbers look good, strange, or risky and you need to know whether the experiment can actually be trusted.

What it does:
	•	checks for peeking
	•	checks stopping logic
	•	checks allocation and contamination risks
	•	returns a trust verdict

This is also calculation-aware and has a REFERENCE.md.

⸻

8. recommend-post-test-decision

Use this when the team needs a practical next step.

What it does:
	•	recommends rollout, rerun, iteration, segment rollout, or rejection
	•	takes into account result quality, effect size, guardrails, and business context
	•	avoids fake certainty when key inputs are missing

⸻

How to use this section

There are two normal ways to work with this domain.

Option 1: start from the top

Use this when you only have an idea or a product problem.

Typical path:
	•	formulate-experiment-hypothesis
	•	validate-hypothesis-quality
	•	define-success-metrics
	•	estimate-sample-size
	•	design-experiment-plan

Option 2: enter in the middle

Use this when you already have something concrete.

Examples:
	•	hypothesis already exists → start with validate-hypothesis-quality
	•	metrics are already defined → go to estimate-sample-size
	•	test is complete → start with analyze-experiment-results
	•	results are analyzed but trust is unclear → use validate-experiment-quality
	•	need final action → use recommend-post-test-decision

⸻

How the skills connect

Claude skills cannot rely on hardcoded cross-skill calls like “go run skill X now”.

Because of that, each skill in this domain includes soft bridges:
	•	Upstream context
what should ideally already exist
	•	If upstream context is missing
how the skill should behave when context is incomplete
	•	Downstream handoff
what the output should prepare for next

That is how the skills connect to each other in practice.

⸻

Context matters

These skills are built to behave differently depending on how much context is available.

Rich context

The skill can be specific and close to execution-ready.

Light context

The skill should stay useful, but clearly mark what is still missing.

Poor context

The skill should not pretend to know the product or business.
It should switch into discovery or setup mode instead of inventing certainty.

This is especially important in experimentation, because bad assumptions early in the chain create bad decisions later.

⸻

Examples and references

Each skill has an examples/ folder.

Examples are there to show:
	•	what kind of input the skill can handle
	•	what good output looks like
	•	how the skill behaves under different levels of context or input completeness

Some skills also include a REFERENCE.md.

Use REFERENCE.md when the skill depends on:
	•	formulas
	•	statistical assumptions
	•	interpretation rules
	•	caveats
	•	invalid-use conditions

In short:
	•	examples/ show behavior
	•	REFERENCE.md explains methodology

⸻

Skill types in this domain

Conceptual skills

These are mostly about structuring the work:
	•	formulate-experiment-hypothesis
	•	validate-hypothesis-quality
	•	define-success-metrics
	•	design-experiment-plan
	•	recommend-post-test-decision

Calculation-aware skills

These depend on real assumptions and should not fake precision:
	•	estimate-sample-size
	•	analyze-experiment-results
	•	validate-experiment-quality

⸻

Folder structure
experimentation/
├── README.md
└── skills/
    ├── formulate-experiment-hypothesis/
    ├── validate-hypothesis-quality/
    ├── define-success-metrics/
    ├── estimate-sample-size/
    ├── design-experiment-plan/
    ├── analyze-experiment-results/
    ├── validate-experiment-quality/
    └── recommend-post-test-decision/

Inside each skill folder:
	•	Skill.md is the main instruction file
	•	examples/ contains usage examples
	•	REFERENCE.md exists where deeper methodology is needed
	•	scripts/ exists only where code helpers may be useful later

⸻

What this domain tries to protect against

This section is not only about running experiments.
It is also about avoiding bad experimentation habits.

Common failure modes:
	•	vague hypotheses
	•	wrong metrics
	•	fake precision
	•	using total traffic instead of eligible traffic
	•	treating p-value as a shipping rule
	•	ignoring guardrails
	•	trusting a test that was peeked at or stopped early
	•	making confident business decisions from weak evidence

A lot of the structure here exists specifically to reduce those mistakes.

⸻

Where to start

If you are new to this section:
	1.	read this README
	2.	open the skill that matches your current stage
	3.	read its Skill.md
	4.	check the examples
	5.	open REFERENCE.md only if the skill is calculation-aware or you need the deeper rules


