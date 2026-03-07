---
name: validate-hypothesis-quality
description: Evaluate whether a product experiment hypothesis is specific, measurable, and suitable for testing. Use this skill when the user already has a draft hypothesis and wants to know if it is strong enough for an A/B test or other product experiment.
---

# Validate Hypothesis Quality

## Purpose
Assess whether a hypothesis is good enough to support experiment design.

## Skill type
Conceptual skill with readiness checks for downstream calculation-aware skills

## Use this skill when
- The user already has a draft hypothesis
- The user wants to know whether a hypothesis is testable
- The user wants to improve a vague or weak experiment idea
- Another skill has produced a first-pass hypothesis and it needs validation

## Required inputs
- Hypothesis statement

## Optional inputs
- Product context
- Business goal
- Target segment
- Metric tree
- Funnel context
- Constraints

## Additional resources

### Use examples/ when
- you need to see what good input/output looks like
- you need to match the expected output structure
- you need to see how this skill behaves under rich, light, or poor context

### Use REFERENCE.md when
- this skill includes one and you need additional decision rules
- you need deeper context-handling guidance
- you need edge cases or caveats not included in the main instructions

### Resource priority
1. Read this Skill.md first
2. Use examples/ for behavior patterns and output structure
3. Use REFERENCE.md for deeper rules, caveats, and edge cases

## Upstream context
This skill works best when at least some upstream framing already exists:
- a draft hypothesis
- a rough product area
- a target segment or likely audience
- a likely outcome metric
- some reason the change should work

## If upstream context is missing
If the hypothesis is too abstract or the product context is absent, validate it only at exploration level.
Do not mark it as ready for experiment design if segment, metric, or causal logic are still unknown.

## Downstream handoff
A strong output from this skill should be usable by:
- define-success-metrics
- estimate-sample-size
- design-experiment-plan

A good handoff includes:
- verdict
- improved hypothesis
- readiness state
- missing inputs for next step

## Context collection rules
### Context-rich
Evaluate the hypothesis against the real product flow, real segment, and real metric vocabulary.

### Context-light
Validate the structure of the hypothesis, but explicitly flag missing context that blocks experiment design.

### Context-poor
Do not pretend the hypothesis is experiment-ready.
Validate only at exploration level and say what minimum context is needed before approval for design.

## Minimum context to collect before declaring “valid for experiment design”
- target segment
- likely primary metric
- clear product area or change
- plausible causal mechanism
- basic business relevance

## Instructions
1. Check whether the hypothesis contains a specific change.
2. Check whether it names or strongly implies a measurable outcome.
3. Check whether the target segment is clear.
4. Check whether there is a plausible causal mechanism.
5. Check whether success can be evaluated objectively.
6. Check whether multiple changes are mixed into one hypothesis.
7. Check whether expected effect magnitude or minimum meaningful effect is defined.
8. Classify the hypothesis into one of these states:
   - Valid for exploration
   - Valid for experiment design
   - Weak
   - Invalid
9. If weak or invalid, rewrite it into a stronger version.
10. If it is valid for exploration but not yet valid for experiment design, list what is still needed.

## Output
Provide:
- Verdict
- Main weaknesses
- Improved version
- Missing information
- Readiness for next step
- Context gaps blocking the next step

## Risks / caveats
- Do not require exact numbers at ideation stage
- Do require measurement logic before passing to sample size estimation
- Do not approve hypotheses that cannot produce a clear success/failure decision
