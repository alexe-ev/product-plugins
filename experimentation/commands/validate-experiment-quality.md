---
description: Audit whether a product experiment was designed and run in a way that makes the result trustworthy. Use this skill when the user wants to check for issues such as peeking, invalid stopping logic, traffic imbalance, contamination, or other threats to validity.
---

Ask the user for: experiment design summary, experiment execution summary. Optionally: sample sizes, assignment logs, exposure logs, interim check behavior, stop logic, time window, external events, guardrail behavior.

Apply the skill at skills/validate-experiment-quality/SKILL.md and REFERENCE.md.

If required inputs are missing, list them and stop. Output: quality verdict, major risks, reliability level, fatal vs manageable issues, recommendation, missing procedural evidence.
