---
name: model-ltv-cac
description: Model customer lifetime value (LTV) and customer acquisition cost (CAC) to assess unit economics and growth sustainability. Use this skill when a team needs to understand whether the business model is economically sustainable.
---

# Model LTV:CAC

## Purpose
Help teams calculate, interpret, and improve the LTV:CAC ratio — the foundational unit economics metric that determines whether growth is creating or destroying value.

## Skill type
Conceptual skill with calculation-aware components

## Use this skill when
- The team doesn't know if growth is economically sustainable
- LTV or CAC metrics exist but aren't being compared or interpreted correctly
- A pricing or acquisition model change needs impact assessment on LTV:CAC
- An investor or leadership asks about unit economics

## Do not use this skill when
- The goal is general revenue forecasting (use run-forecasting-scenarios)
- The goal is pricing structure (use support-pricing-packaging)

## Required inputs
- Average revenue per customer (monthly or annual)
- Gross margin
- Average customer lifetime or churn rate
- CAC estimate

## Optional inputs
- CAC breakdown by channel
- LTV by segment or cohort
- Payback period data
- Industry benchmarks

## Upstream context
Works best when:
- Revenue model is defined
- Churn data exists

## Downstream handoff
Output can feed:
- build-business-case (LTV:CAC is a core business case input)
- align-revenue-strategy (unit economics informs revenue strategy)
- strategize-channel-campaigns (CAC by channel feeds channel strategy)

## Instructions
1. Calculate LTV: (Average Revenue per Customer × Gross Margin) ÷ Churn Rate.
2. Calculate CAC: Total Sales and Marketing Spend ÷ New Customers Acquired.
3. Calculate LTV:CAC ratio and payback period.
4. Assess the ratio against benchmarks (typically: >3x LTV:CAC is healthy; <12 month payback is strong).
5. Break down CAC by channel if data allows.
6. Identify the biggest levers to improve the ratio.
7. Model what the ratio looks like at different scale or with proposed changes.

## Output
Provide:
- LTV calculation with inputs and formula
- CAC calculation with inputs
- LTV:CAC ratio and payback period
- Benchmark comparison
- Ratio interpretation (healthy / marginal / unsustainable)
- CAC by channel (if available)
- Top improvement levers with estimated impact
- Model at different scale or with proposed changes

## Risks / caveats
- LTV is often overestimated with optimistic churn assumptions — use actual cohort data
- CAC must include all S&M costs, not just paid advertising
- LTV:CAC above 10x sometimes signals underinvestment in growth, not just efficiency
