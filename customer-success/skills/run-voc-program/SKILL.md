---
name: run-voc-program
description: Design and operate a Voice of Customer program that surfaces systematic insights from customers. Use this skill when a team needs a structured system for collecting and acting on customer feedback.
---

# Run Voice of Customer Program

## Purpose
Help teams design and operate a Voice of Customer (VoC) program that systematically surfaces customer insights and routes them to product decisions.

## Skill type
Conceptual skill

## Use this skill when
- Customer feedback is scattered and not systematically collected
- The team doesn't have a regular cadence of customer insight review
- A VoC program exists but insights don't reach product teams
- A new product or segment needs a customer feedback system

## Do not use this skill when
- The goal is a single user research study (use plan-ux-research)
- The goal is analyzing specific churn data (use analyze-churn-retention)

## Required inputs
- Product type and customer segment
- Current state of customer feedback collection (even if none)

## Optional inputs
- Existing feedback channels (NPS, CSAT, support tickets, reviews)
- Team capacity for running the program
- Stakeholder requirements

## Upstream context
Works best when:
- Customer segments are defined
- Product goals and metrics exist

## Downstream handoff
Output can feed:
- triage-feedback-loop
- synthesize-qualitative-research (VoC findings need synthesis)
- identify-problem-opportunity

## Instructions
1. Audit current feedback channels and coverage.
2. Design the VoC program structure: channels, frequency, audience.
3. Define how insights are collected, tagged, and aggregated.
4. Design the synthesis and review cadence.
5. Define how VoC insights are routed to product decisions.
6. Identify metrics for program effectiveness.

## Output
Provide:
- Feedback channel audit
- VoC program structure (channels, frequency, audience, collection method)
- Synthesis and tagging methodology
- Review cadence design
- Routing protocol: from insight to product decision
- Program effectiveness metrics

## Risks / caveats
- Collecting feedback without acting on it damages customer trust
- Loudest customers ≠ most representative customers — design for systematic sampling
- VoC programs require dedicated maintenance — underfunded programs decay quickly
