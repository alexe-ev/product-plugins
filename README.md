# AI Product Ops

Your AI agent doesn't know how to think like a product manager. This library fixes that.

121 skills across 15 domains, each one a structured playbook: what to ask, how to reason, what to output. Install the domains you need, skip the rest.

```bash
claude plugin install ai-product-ops/experimentation
# now Claude knows how to design experiments, size samples, and read results
```

---

## What this looks like in practice

Running an A/B test and need to know if you have enough traffic:
```
/experimentation:estimate-sample-size
```

Metric dropped 12% last week and nobody knows why:
```
/data-analytics:diagnose-metric-movement
```

Investor deck needs a real business case, not vibes:
```
/business-commercial:build-business-case
```

Stakeholders are misaligned on the roadmap, again:
```
/product-planning:build-roadmap-prioritization
```

Each command walks Claude through the right questions, the right methodology, and the right output format for that specific task.

---

## 15 domains, 121 skills

| Plugin | What it covers |
|--------|----------------|
| `experimentation` | Hypothesis design, sample sizing, experiment plans, result analysis, post-test decisions |
| `data-analytics` | Metrics frameworks, funnel analysis, dashboards, signal detection, metric diagnosis |
| `product-strategy` | Vision, long-term direction, market fit, positioning, competitive strategy, portfolio |
| `product-discovery` | Problem framing, user interviews, JTBD, insight synthesis, opportunity identification |
| `product-planning` | OKRs, roadmapping, prioritization, PRDs, user stories, delivery planning |
| `gtm` | Launch planning, positioning, messaging, pricing, sales battlecards, enablement |
| `marketing-growth` | Growth models, acquisition funnels, lifecycle, onboarding, conversion, channel experiments |
| `ai-product` | AI feature ideation, model tradeoffs, HITL workflows, quality monitoring, value framing |
| `business-commercial` | Business cases, unit economics, LTV/CAC, forecasting, ROI, revenue strategy |
| `customer-success` | Churn analysis, health scoring, VOC programs, feedback triage, retention playbooks |
| `product-ops` | Operating cadence, planning processes, tooling, cross-team alignment, wikis |
| `leadership-communication` | Executive narratives, stakeholder mapping, decision frameworks, team rituals |
| `technical-product` | Platform thinking, architecture-aware prioritization, engineering collaboration, NFRs |
| `risk-compliance` | Risk registers, privacy assessment, ethical frameworks, responsible AI governance |
| `ux-research` | Research planning, usability testing, journey mapping, experience quality, design handoff |

Install any combination:

```bash
claude plugin install ai-product-ops/experimentation
claude plugin install ai-product-ops/data-analytics
claude plugin install ai-product-ops/product-strategy
```

---

## Does it actually work?

Skills in the `experimentation` domain were benchmarked against a vanilla Claude (same model, no skill) across multiple scenarios: complete inputs, missing inputs, and edge cases like unsafe traffic assumptions.

| Skill | With skill | Without skill | Delta |
|-------|-----------|---------------|-------|
| `formulate-experiment-hypothesis` | 100% | 37% | +63pp |
| `validate-hypothesis-quality` | 100% | 60% | +40pp |
| `define-success-metrics` | 100% | 71% | +29pp |
| `estimate-sample-size` | 100% | 87% | +13pp |

Skills score 100% with zero variance across all runs. The baseline varies widely, and the gap widens on harder scenarios.

What the skill actually prevents:

- **Fabricated numbers.** Without the skill, the model invents concrete targets ("this will improve conversion by 30%") in 2 out of 3 runs on ambiguous inputs. The skill stops and asks instead.
- **Scope creep.** Without the skill, a hypothesis prompt sometimes ballooned into a full experiment design (100s response time vs 10-22s). The skill stays on task.
- **Wrong behavior on missing inputs.** Without the skill, the model confidently commits to a primary metric even when inputs are ambiguous. The skill flags it as provisional and lists what's missing.

The biggest gains are on fuzzy inputs — exactly the situations that come up in real product work.

---

## Skill structure

Every skill is a standalone playbook:

```
experimentation/skills/estimate-sample-size/
├── SKILL.md        ← what to ask, how to reason, what to output
├── REFERENCE.md    ← formulas and methodology (calculation skills)
└── examples/       ← how the skill behaves with complete vs. incomplete inputs
```

Skills don't hallucinate methodology. If required inputs are missing, they stop and ask. If the math is uncertain, they say so.

---

## Install a single skill without the plugin

```bash
cp -r experimentation/skills/estimate-sample-size ~/.claude/skills/
```

---

## Who built this

[Evgeny Alexeev](https://github.com/alexe-ev), Lead PM. Built this to stop re-explaining product methodology to AI agents on every project.
