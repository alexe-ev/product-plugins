# In-App Upgrade Prompt Testing Strategy
## B2B Project Management Tool - Collaborator Limit Trigger

---

## Executive Summary

Testing an in-app upgrade prompt triggered at the collaborator limit on free plans is a high-intent moment for conversion. This document outlines success metrics, implementation considerations, and optimization strategies to maximize the conversion impact.

---

## 1. Core Success Metrics

### Primary Metrics (Direct Impact on Revenue)

#### 1.1 Upgrade Conversion Rate
- **Definition**: Percentage of users who see the prompt and complete an upgrade purchase
- **Target**: Establish baseline first, then aim for 3-8% conversion (typical B2B SaaS range)
- **Tracking**: Prompt viewed → Upgrade button clicked → Payment completed
- **Why it matters**: Direct measure of revenue impact

#### 1.2 Revenue per Prompted User (RPU)
- **Definition**: Total revenue generated divided by number of users shown the prompt
- **Calculation**: (Successful upgrades × avg plan price) / Total prompted users
- **Target**: $5-15 RPU depending on plan pricing
- **Why it matters**: Captures both conversion rate and plan tier selection

#### 1.3 Customer Lifetime Value (CLV) Lift
- **Definition**: Increase in CLV for users who upgrade via this prompt vs. control group
- **Tracking**: Monitor upgrade cohort for 6-12 months post-conversion
- **Why it matters**: Ensures conversions are sustainable, not one-time purchases

---

## 2. Secondary Engagement Metrics

### 2.1 Prompt Engagement
- **View Rate**: % of users who reach the collaborator limit
- **Click-Through Rate (CTR)**: % of viewers who click "Learn More" or similar
- **Dismiss Rate**: % who close without interacting
- **Target**: CTR 15-25% for in-context prompts

### 2.2 User Flow Completion
- **Users Who Complete Checkout**: % of click-throughs who finish payment
- **Cart Abandonment Rate**: % who enter checkout but don't complete
- **Target**: 60-75% checkout completion for high-intent users

### 2.3 Feature Adoption Post-Upgrade
- **Active Collaborators Added**: Measure if users actually utilize increased limits
- **Seats Used vs. Purchased**: Track seat utilization post-upgrade
- **Why it matters**: Indicates satisfaction and prevents early churn

---

## 3. User Experience Metrics

### 3.1 Task Completion Impact
- **Definition**: Whether the prompt blocks or allows users to continue their current task
- **Metric**: Ability to invite collaborator while prompt is displayed
- **Target**: Minimize friction—allow task completion after upgrade or during trial
- **Why it matters**: Poor UX can drive users to competitors

### 3.2 Friction Score
- **Prompt Interruption Level**: Measure time on page increase before/after prompt display
- **Session Duration**: Does the prompt cause session drop-off?
- **Return Rate**: 7-day and 30-day return rates for non-converted users
- **Target**: Maintain 90%+ return rate for non-converted users

### 3.3 Sentiment & Feedback
- **In-app Surveys**: "Was this upgrade prompt helpful?" (1-5 scale)
- **Support Ticket Analysis**: Track complaints mentioning upgrade prompts
- **Target**: Maintain >3.5/5 average sentiment

---

## 4. Segmentation & Cohort Analysis

### 4.1 User Segment Performance
Track metrics separately by:
- **Company Size**: Solo, small team (2-5), medium (6-20), enterprise (20+)
- **Team Role**: Admin, manager, individual contributor
- **Usage Pattern**: Power users (daily), regular (weekly), casual (monthly)
- **Why it matters**: Identify which segments convert best

### 4.2 Plan Tier Upgrade Path
- **Conversion by Target Plan**: % upgrading to Starter vs. Pro vs. Enterprise
- **Upgrade Value**: Average plan value by cohort
- **Why it matters**: Reveals willingness-to-pay and optimal positioning

### 4.3 Timing Analysis
- **Days to Upgrade**: How long after hitting limit do users convert?
- **Session Velocity**: Same session conversion vs. return users
- **Target**: 40% same-session conversion, 80% within 7 days

---

## 5. Business Impact Metrics

### 5.1 Incrementality & Attribution
- **Incremental Revenue**: Revenue from prompt vs. counterfactual (control group)
- **Control Group**: Users who hit limit but don't see prompt (holdout testing)
- **Calculation**: (Upgraded with prompt - Upgraded without prompt) × avg plan value
- **Why it matters**: Ensures metric lift isn't from users who would upgrade anyway

### 5.2 Cost Analysis
- **CAC Reduction**: Cost to acquire customer via prompt vs. traditional channels
- **Payback Period**: How quickly does customer LCV repay acquisition cost
- **Why it matters**: Validates business model sustainability

### 5.3 Churn Impact
- **Churn Rate Comparison**: Upgraded users vs. non-converted free users
- **Target**: Churn within 6 months should be <15% for B2B SaaS
- **Why it matters**: Ensures quality of conversions

---

## 6. Technical Implementation Metrics

### 6.1 Reliability
- **Prompt Display Rate**: % of collaborator limit hits that successfully trigger prompt
- **Target**: 99%+ reliability
- **Error Rate**: Failed payment processing, timeout issues

### 6.2 Performance
- **Page Load Impact**: Does prompt slow page load significantly?
- **Rendering Time**: Time from limit hit to prompt display
- **Target**: <200ms prompt display latency

---

## 7. A/B Testing Framework

### 7.1 Test Design
- **Control Group**: Users hitting collaborator limit without prompt (20-30% holdout)
- **Treatment Group**: Users shown upgrade prompt
- **Duration**: Minimum 2-4 weeks to capture weekly and monthly user patterns
- **Sample Size**: Ensure 95% statistical confidence at 80% power

### 7.2 Test Variants to Consider
- **Prompt Timing**: Show immediately vs. after 1-minute delay
- **Copy Variations**: Urgency messaging vs. value-driven messaging
- **CTA Button**: "Upgrade Now" vs. "Start Free Trial" vs. "Learn More"
- **Design**: Modal popup vs. inline banner vs. slide-out panel

### 7.3 Statistical Significance
- **Primary Metric**: Upgrade conversion rate
- **Minimum Detectable Effect (MDE)**: 2-3% relative lift (0.5-1.5 percentage points)
- **Calculate**: Sample size needed for reliable results

---

## 8. Key Success Indicators (KSIs)

| Metric | Target | Priority |
|--------|--------|----------|
| Upgrade Conversion Rate | 3-8% | P0 (Primary) |
| Revenue per Prompted User | $5-15 | P0 (Primary) |
| Click-Through Rate | 15-25% | P1 (Secondary) |
| Checkout Completion Rate | 60-75% | P1 (Secondary) |
| 30-Day Return Rate (Non-converted) | >90% | P1 (Secondary) |
| Prompt Display Reliability | 99%+ | P2 (Reliability) |
| Incrementality (Control vs. Treatment) | >0% net lift | P0 (Critical) |

---

## 9. Guardrails & Risk Mitigation

### 9.1 Negative Outcome Indicators
- **Conversion Rate Decline**: If prompt decreases overall conversions <-2%
- **Churn Spike**: If 30-day churn increases for non-converted users >5%
- **Support Burden**: If prompt-related support tickets spike >20%
- **Action**: Pause test and iterate prompt messaging/design

### 9.2 Fairness & Ethics
- **Avoid Dark Patterns**: Don't use aggressive urgency (fake scarcity, countdown timers)
- **Transparency**: Clearly communicate plan limitations upfront
- **Option to Dismiss**: Always provide an easy "No thanks" option
- **Why it matters**: Maintains brand trust and reduces churn post-upgrade

---

## 10. Measurement Tools & Implementation

### 10.1 Analytics Setup
- **Event Tracking**: Prompt viewed, CTA clicked, upgrade started, upgrade completed
- **User Properties**: User segment, plan tier, account age, team size
- **Session Analytics**: Entry point, duration, subsequent actions

### 10.2 Data Integration
- **Payment System**: Capture upgrade events from billing platform
- **Product Analytics**: Segment events by product behavior (collaborator limit hit)
- **CRM/Data Warehouse**: Join for long-term LTV and churn tracking

### 10.3 Reporting Dashboard
- **Real-time**: Conversion rate, CTR, prompts shown
- **Daily**: Revenue by plan tier, segment performance
- **Weekly**: Cohort analysis, churn trends, support volume

---

## 11. Iteration Plan

### Phase 1: Baseline (Week 1-2)
- Launch initial prompt design
- Measure baseline conversion rate
- Identify technical issues

### Phase 2: Optimization (Week 3-6)
- Test 2-3 variants of copy, design, CTA
- Analyze segment-level performance
- Optimize for highest-converting cohort

### Phase 3: Scaling (Week 7+)
- Roll out winning variant to 100% of eligible users
- Monitor long-term churn and LTV
- Plan next optimization cycle

---

## 12. Conclusion

This in-app upgrade prompt targets a high-intent moment—when users directly encounter a product limitation. Success depends on:

1. **Accurate measurement** of incrementality (control group essential)
2. **Segment-level optimization** (different cohorts may have different needs)
3. **User-first design** (avoid dark patterns)
4. **Long-term value tracking** (monitor churn, not just conversion)
5. **Continuous iteration** (test copy, timing, design variants)

By tracking the metrics outlined above, you'll have clear visibility into whether this prompt drives sustainable, profitable growth for your B2B SaaS product.
