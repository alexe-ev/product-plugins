# AI Product Plugins

[![Skills](https://img.shields.io/badge/skills-121-blue)]() [![Domains](https://img.shields.io/badge/domains-15-green)]() [![License](https://img.shields.io/badge/license-MIT-brightgreen)](#license)

Your AI agent doesn't know how to think like a product manager. This library fixes that.

121 skills across 15 domains, each one a structured playbook: what to ask, how to reason, what to output. Install the domains you need, skip the rest.

---

## Quick start

**1. Install a domain**

```bash
claude plugin install ai-product-ops/experimentation
```

**2. Use a skill**

```
/experimentation:estimate-sample-size
```

**3. Follow the prompts**

The skill walks Claude through the right questions, methodology, and output format. If required inputs are missing, it stops and asks — no hallucinated numbers, no guesswork.

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

| Domain | What it covers | Skills |
|--------|----------------|--------|
| `experimentation` | Hypothesis design, sample sizing, experiment plans, result analysis, post-test decisions | 8 |
| `data-analytics` | Metrics frameworks, funnel analysis, dashboards, signal detection, metric diagnosis | 8 |
| `product-strategy` | Vision, long-term direction, market fit, positioning, competitive strategy, portfolio | 9 |
| `product-discovery` | Problem framing, user interviews, JTBD, insight synthesis, opportunity identification | 8 |
| `product-planning` | OKRs, roadmapping, prioritization, PRDs, user stories, delivery planning | 8 |
| `gtm` | Launch planning, positioning, messaging, pricing, sales battlecards, enablement | 8 |
| `marketing-growth` | Growth models, acquisition funnels, lifecycle, onboarding, conversion, channel experiments | 8 |
| `ai-product` | AI feature ideation, model tradeoffs, HITL workflows, quality monitoring, value framing | 8 |
| `business-commercial` | Business cases, unit economics, LTV/CAC, forecasting, ROI, revenue strategy | 8 |
| `customer-success` | Churn analysis, health scoring, VOC programs, feedback triage, retention playbooks | 8 |
| `product-ops` | Operating cadence, planning processes, tooling, cross-team alignment, wikis | 8 |
| `leadership-communication` | Executive narratives, stakeholder mapping, decision frameworks, team rituals | 8 |
| `technical-product` | Platform thinking, architecture-aware prioritization, engineering collaboration, NFRs | 8 |
| `risk-compliance` | Risk registers, privacy assessment, ethical frameworks, responsible AI governance | 8 |
| `ux-research` | Research planning, usability testing, journey mapping, experience quality, design handoff | 8 |

Install any combination:

```bash
claude plugin install ai-product-ops/experimentation
claude plugin install ai-product-ops/data-analytics
claude plugin install ai-product-ops/product-strategy
```

Or install a single skill without the full plugin:

```bash
cp -r experimentation/skills/estimate-sample-size ~/.claude/skills/
```

<details>
<summary><strong>Full skill list by domain</strong></summary>

### experimentation
| Skill | Description |
|-------|-------------|
| `formulate-experiment-hypothesis` | Turn a product idea into a testable hypothesis |
| `validate-hypothesis-quality` | Check if a hypothesis is specific, measurable, and testable |
| `define-success-metrics` | Define primary metric, secondary metrics, and guardrails |
| `estimate-sample-size` | Calculate required sample size and experiment duration |
| `design-experiment-plan` | Build a complete experiment plan from hypothesis to execution |
| `analyze-experiment-results` | Analyze control vs test results with statistical rigor |
| `validate-experiment-quality` | Audit whether an experiment was run correctly |
| `recommend-post-test-decision` | Recommend next steps based on experiment outcome |

### data-analytics
| Skill | Description |
|-------|-------------|
| `design-product-metrics` | Define a metrics framework with primary, secondary, and guardrail metrics |
| `analyze-funnel-retention-cohorts` | Analyze funnel drop-off, retention curves, and cohort behavior |
| `build-decision-dashboard` | Structure a dashboard that supports fast decision-making |
| `design-metric-alert-system` | Design alerting with thresholds, logic, and escalation paths |
| `detect-performance-signals` | Identify and interpret signals of product performance change |
| `diagnose-metric-movement` | Diagnose root cause of unexpected metric movements |
| `plan-event-instrumentation` | Plan event tracking and instrumentation for product analytics |
| `run-cohort-analysis` | Structure and interpret cohort analysis for retention and behavior |

### product-strategy
| Skill | Description |
|-------|-------------|
| `define-product-vision` | Articulate a clear product vision |
| `craft-product-mission` | Define the product mission statement |
| `define-long-term-direction` | Translate vision into strategic priorities and trade-offs |
| `define-strategic-positioning` | Define how the product is positioned in the market |
| `assess-product-market-fit` | Evaluate product-market fit signals |
| `analyze-competitive-landscape` | Map competitive landscape and dynamics |
| `frame-competitive-differentiation` | Frame what differentiates the product from alternatives |
| `build-portfolio-roadmap-strategy` | Build a portfolio-level roadmap strategy |
| `prioritize-strategic-bets` | Prioritize strategic bets and investment areas |

### product-discovery
| Skill | Description |
|-------|-------------|
| `identify-problem-opportunity` | Frame the real problem or opportunity before jumping to solutions |
| `scope-discovery-research` | Define scope, goals, and methods for discovery research |
| `run-user-interviews` | Plan, structure, and synthesize user interviews |
| `apply-jtbd-framework` | Apply Jobs-to-be-Done to understand what job users hire the product for |
| `synthesize-qualitative-research` | Synthesize interviews and qualitative data into actionable insights |
| `generate-insights` | Distill raw observations into meaningful product insights |
| `frame-insight-opportunity` | Turn insights into structured opportunity statements |
| `develop-persona-segment` | Build and validate user personas and segments |

### product-planning
| Skill | Description |
|-------|-------------|
| `set-goals-okrs-kpis` | Define and structure goals using OKRs and KPIs |
| `align-goals-to-strategy` | Check alignment between team goals and company strategy |
| `build-roadmap-prioritization` | Build and prioritize a feature or initiative roadmap |
| `apply-prioritization-framework` | Apply RICE, MoSCoW, ICE, or opportunity scoring |
| `write-requirements-prd` | Write complete product requirements documents |
| `write-user-stories` | Write user stories with clear acceptance criteria |
| `plan-delivery-collaboration` | Structure delivery planning and cross-functional alignment |
| `run-retrospective` | Facilitate a retrospective to extract learning |

### gtm
| Skill | Description |
|-------|-------------|
| `plan-product-launch` | Build a launch plan with timeline, channels, and coordination |
| `build-launch-readiness-checklist` | Cover all cross-functional dependencies before launch |
| `develop-positioning-messaging` | Develop positioning and messaging for target segments |
| `craft-value-proposition` | Craft a clear value proposition for a product or feature |
| `design-packaging-tiers` | Design packaging tiers aligned with value and willingness to pay |
| `support-pricing-packaging` | Analyze and recommend pricing structures |
| `create-sales-battlecard` | Create competitive battlecards for sales |
| `enable-sales-cs` | Structure sales and CS enablement materials |

### marketing-growth
| Skill | Description |
|-------|-------------|
| `design-growth-model` | Build or assess a growth model (AARRR) |
| `map-acquisition-funnel` | Map acquisition funnel from awareness to activation |
| `identify-growth-loop` | Identify and map compounding growth loops |
| `optimize-conversion-growth-loops` | Identify conversion bottlenecks and reinforce growth loops |
| `design-onboarding-flow` | Design onboarding that gets users to activation fast |
| `plan-lifecycle-engagement` | Design lifecycle engagement including onboarding and re-engagement |
| `design-channel-experiment` | Design a structured experiment for a new growth channel |
| `strategize-channel-campaigns` | Develop channel strategy and campaign experimentation plan |

### ai-product
| Skill | Description |
|-------|-------------|
| `ideate-ai-features` | Generate AI feature ideas with value propositions and feasibility |
| `assess-model-capabilities` | Evaluate AI model capabilities and limitations for a product decision |
| `make-model-tradeoff-decision` | Structure trade-offs between AI models or approaches |
| `frame-ai-product-value` | Frame AI feature value in terms of user outcomes |
| `design-human-in-loop-workflow` | Balance AI automation with human oversight |
| `define-ai-success-metrics` | Define success metrics covering quality, UX, business, and safety |
| `evaluate-ai-quality-monitoring` | Set up AI quality monitoring and evaluation loops |
| `run-ai-prototype-evaluation` | Evaluate an AI prototype for quality and readiness |

### business-commercial
| Skill | Description |
|-------|-------------|
| `build-business-case` | Develop a structured business case with ROI and risks |
| `frame-roi-analysis` | Frame ROI analysis for a product initiative |
| `analyze-unit-economics` | Analyze CAC, LTV, payback period, and gross margin |
| `model-ltv-cac` | Model LTV and CAC for unit economics assessment |
| `evaluate-pricing-model` | Evaluate pricing model against behavior and goals |
| `align-revenue-strategy` | Align product decisions with revenue model and commercial goals |
| `run-forecasting-scenarios` | Build and compare forecasting scenarios |
| `run-sensitivity-analysis` | Identify which assumptions have the most impact |

### customer-success
| Skill | Description |
|-------|-------------|
| `analyze-churn-retention` | Analyze churn patterns and design retention interventions |
| `build-customer-health-score` | Build a health score model predicting churn and expansion |
| `monitor-adoption-health` | Define and monitor adoption health metrics |
| `run-voc-program` | Design a Voice of Customer program for systematic insights |
| `design-customer-feedback-survey` | Design surveys that generate reliable, actionable data |
| `synthesize-feedback-themes` | Synthesize feedback volumes into structured themes |
| `triage-feedback-loop` | Establish feedback intake and triage routing |
| `design-retention-playbook` | Design retention playbook for at-risk accounts |

### product-ops
| Skill | Description |
|-------|-------------|
| `design-operating-cadence` | Design operating rhythm: meetings, reviews, reporting, planning |
| `design-planning-process` | Connect strategy to execution through repeatable planning |
| `align-cross-team-communication` | Design communication systems that keep teams aligned |
| `run-cross-functional-review` | Facilitate cross-functional product review for alignment |
| `audit-product-process` | Identify bottlenecks and improvement opportunities |
| `automate-workflow-governance` | Identify automation opportunities and governance standards |
| `manage-tooling-documentation` | Audit tooling stacks and documentation practices |
| `build-product-wiki` | Design and populate a product knowledge base |

### leadership-communication
| Skill | Description |
|-------|-------------|
| `build-executive-narrative` | Craft executive-level narratives about strategy and results |
| `write-product-strategy-doc` | Write a product strategy document that aligns teams |
| `communicate-decisions-tradeoffs` | Communicate decisions and trade-offs to build trust |
| `apply-decision-framework` | Apply DACI, SPADE, RAPID for clear decisions |
| `map-stakeholder-influence` | Map stakeholders and develop engagement strategies |
| `run-stakeholder-alignment` | Execute stakeholder alignment for decisions or initiatives |
| `build-operating-norms` | Establish team operating norms and working agreements |
| `design-team-rituals` | Design rituals and rhythms that build alignment |

### technical-product
| Skill | Description |
|-------|-------------|
| `run-technical-discovery` | Surface feasibility constraints and architectural options |
| `collaborate-with-engineering` | Structure product-engineering collaboration patterns |
| `define-non-functional-requirements` | Define performance, security, scalability, accessibility, compliance |
| `prioritize-architecture-aware` | Incorporate architectural constraints into prioritization |
| `manage-technical-debt-tradeoffs` | Structure trade-offs between tech debt and new value |
| `develop-platform-product-thinking` | Define developer experience, extensibility, ecosystem strategy |
| `design-developer-experience` | Design DX for platform, API, or SDK products |
| `assess-reliability-scalability` | Evaluate reliability and scalability for product decisions |

### risk-compliance
| Skill | Description |
|-------|-------------|
| `run-pre-mortem` | Identify ways an initiative could fail before launch |
| `design-risk-register` | Design and populate a risk register for an initiative |
| `plan-risk-mitigation` | Develop mitigation plans with owners, triggers, contingencies |
| `assess-privacy-security-regulatory` | Identify privacy, security, and regulatory risks |
| `run-privacy-impact-assessment` | Run a PIA for features that handle personal data |
| `apply-ethical-decision-framework` | Apply ethical frameworks to evaluate product decisions |
| `conduct-ai-audit` | Audit AI systems against responsible AI standards |
| `govern-responsible-ai` | Establish governance for responsible AI development |

### ux-research
| Skill | Description |
|-------|-------------|
| `plan-ux-research` | Plan UX research initiatives |
| `design-research-study` | Design a structured research study |
| `run-usability-testing` | Plan and run usability testing sessions |
| `analyze-usability-findings` | Analyze and synthesize usability test findings |
| `map-user-journey` | Map the end-to-end user journey |
| `assess-experience-quality` | Assess overall experience quality |
| `manage-design-handoff` | Structure design-to-engineering handoff |
| `write-design-brief` | Write a clear design brief |

</details>

---

## Does it actually work?

Skills in the **`experimentation`** domain were benchmarked against a vanilla Claude (same model, no skill) across multiple scenarios: complete inputs, missing inputs, and edge cases like unsafe traffic assumptions.

| Skill | With skill | Without skill | Delta |
|-------|-----------|---------------|-------|
| `formulate-experiment-hypothesis` | 100% | 37% | +63pp |
| `validate-hypothesis-quality` | 100% | 60% | +40pp |
| `define-success-metrics` | 100% | 71% | +29pp |
| `estimate-sample-size` | 100% | 87% | +13pp |

Skills score 100% with zero variance across all runs. The baseline varies widely, and the gap widens on harder scenarios.

> Benchmarks cover the `experimentation` domain. Other domains follow the same skill structure and methodology but have not been formally benchmarked yet.

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

## Contributing

Contributions are welcome. Whether it's improving an existing skill, adding a new one, or benchmarking another domain — open a PR or issue.

When adding or editing a skill:

1. Follow the existing structure: `SKILL.md` + optional `REFERENCE.md` + `examples/`
2. Include at least one example with complete inputs and one with missing inputs
3. Skills should ask for missing information, not hallucinate it
4. Keep the scope tight — one skill, one job

---

## License

This project is licensed under the [MIT License](LICENSE).
