# AI Product Ops Skill Repository

This repository is the foundational knowledge base and playbook for AI agents supporting product work.

## Purpose

We are building a practical, reusable skill library that helps AI agents contribute across the full product lifecycle—from strategy to execution to scaling operations.

## Who This Is For

- **Product managers and product teams** who want AI agents to assist with experimentation, analytics, strategy, and operations
- **AI engineers** building agent workflows that require structured product expertise
- **Organizations** looking for reusable, quality-controlled skill libraries for their AI tooling

## Current Status

| Domain | Status | Skills |
|--------|--------|--------|
| Experimentation & Optimization | **Ready** | 8 skills covering the full experiment lifecycle |
| Product Strategy | Planned | — |
| Product Discovery & User Research | **Ready** | 8 skills covering the full discovery pipeline |
| Product Planning & Execution | Planned | — |
| UX Research & Design Collaboration | Planned | — |
| Go-to-Market (GTM) | Planned | — |
| Data Analytics & Insights | Planned | — |
| Marketing & Growth | Planned | — |
| Product Operations | Planned | — |
| AI Product Management | Planned | — |
| Technical Product & Platform | Planned | — |
| Customer Success & Feedback | Planned | — |
| Business & Commercial Skills | Planned | — |
| Leadership, Communication & Stakeholders | Planned | — |
| Risk, Compliance & Responsible Development | Planned | — |

## Usage with Claude Code

Skills are located in `.claude/skills/` and follow the Claude Code skill structure. Each skill has:

- `SKILL.md` — main instructions with YAML frontmatter (`name`, `description`)
- `REFERENCE.md` — methodology and formulas (for calculation-aware skills)
- `examples/` — input/output patterns for different context levels
- `scripts/` — helper scripts (if needed)

Canonical skill sources are domain skill directories (e.g. `experimentation/skills/`, `product-discovery/skills/`); `.claude/skills/` contains symlinks for Claude Code discovery.

## Skill Directions (Expertise Areas)

Below is the initial map of skill directions this repository will cover.

### 1. Product Strategy
- Vision, mission, and long-term product direction
- Product-market fit and strategic positioning
- Portfolio and roadmap strategy
- Competitive strategy and differentiation

### 2. Product Discovery & User Research
- Problem discovery and opportunity identification
- User interviews, JTBD, and qualitative research synthesis
- Persona and segment development
- Insight generation and opportunity framing

### 3. Product Planning & Execution
- Goal setting (OKRs, KPIs)
- Roadmapping and prioritization frameworks
- Requirements definition (PRDs, user stories)
- Delivery planning and cross-functional collaboration

### 4. UX Research & Design Collaboration
- UX research planning and methods
- Usability testing and feedback loops
- Experience quality and journey improvement
- Product/design handoff and iteration workflows

### 5. Go-to-Market (GTM)
- Launch strategy and release readiness
- Positioning and messaging
- Pricing and packaging support
- Sales, CS, and enablement collaboration

### 6. Data Analytics & Insights
- Product metrics design and instrumentation
- Funnel, retention, and cohort analysis
- Dashboarding and decision support
- Signal detection and performance diagnostics

### 7. Experimentation & Optimization
- Hypothesis generation and prioritization
- A/B testing design and statistical guardrails
- Experiment execution and readouts
- Rollout, rollback, and scaling decisions

### 8. Marketing & Growth
- Growth model design (acquisition, activation, retention, referral, revenue)
- Lifecycle and engagement strategies
- Channel strategy and campaign experimentation
- Conversion and growth loop optimization

### 9. Product Operations (Product Ops)
- Operating cadence and process design
- Tooling, documentation, and knowledge management
- Cross-team alignment and communication systems
- Workflow automation and governance

### 10. AI Product Management
- AI feature ideation and value framing
- Model capability assessment and trade-off decisions
- Human-in-the-loop workflow design
- AI quality evaluation, monitoring, and iteration

### 11. Technical Product & Platform Collaboration
- API/platform product thinking
- Architecture-aware prioritization
- Engineering collaboration patterns
- Reliability, scalability, and performance considerations

### 12. Customer Success & Feedback Systems
- Voice of customer programs
- Feedback intake and triage loops
- Churn analysis and retention interventions
- Adoption health monitoring

### 13. Business & Commercial Skills
- Business case development
- Unit economics and profitability analysis
- Forecasting and scenario planning
- Revenue strategy alignment

### 14. Leadership, Communication & Stakeholder Management
- Executive communication and narrative building
- Decision-making frameworks and trade-off communication
- Stakeholder mapping and influence strategies
- Team rituals and operating discipline

### 15. Risk, Compliance & Responsible Product Development
- Privacy, security, and regulatory awareness
- Ethical product decision frameworks
- Risk assessment and mitigation planning
- Responsible AI and governance practices

## What's Next

Each direction will get:
1. A dedicated set of skills in `.claude/skills/`
2. Standard workflows and checklists
3. Reusable templates and prompts
4. Quality criteria for AI agent outputs
