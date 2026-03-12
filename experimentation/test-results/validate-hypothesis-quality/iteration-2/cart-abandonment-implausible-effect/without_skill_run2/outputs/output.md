# Hypothesis Evaluation: Cart Abandonment Push Notification

## Hypothesis Statement
*If we add a push notification reminder about an incomplete order 1 hour after abandonment for all mobile users, we expect a 25% increase in completed orders because users often get distracted and forget to return.*

---

## Executive Summary
**Overall Quality Score: 4.2/10 — SIGNIFICANT CONCERNS**
**Readiness for Experimentation: NOT READY**

This hypothesis contains multiple critical issues that make it unsuitable for immediate experimentation without substantial refinement. While the core idea is reasonable, the specified effect size is implausibly large, and the hypothesis lacks crucial specificity about user segments, success metrics, and implementation details.

---

## Detailed Assessment

### 1. HYPOTHESIS STRUCTURE & CLARITY
**Score: 6/10 - Adequate but Incomplete**

**Strengths:**
- Clear causal relationship stated (push notification → order completion)
- Specific timing parameter (1 hour after abandonment)
- Defined target audience (mobile users)
- Explicit expected outcome (25% increase)

**Weaknesses:**
- "Abandoned" is not defined (what triggers an abandonment state?)
- "Completed orders" is ambiguous (does this mean orders that were abandoned but now completed, or completion rate of all mobile users?)
- No specification of how long the effect window is (do we measure for 24 hours, 7 days, 30 days after push?)
- No definition of what constitutes success or failure boundaries

---

### 2. MECHANISTIC REASONING
**Score: 5/10 - Oversimplified**

**The Stated Logic:**
"Users often get distracted and forget to return" → push notification reminder → order completion

**Critical Issues:**

**a) Incomplete Root Cause Analysis**
The hypothesis assumes distraction/forgetfulness is the primary abandonment driver, but research shows multiple drivers:
- Price sensitivity / last-minute hesitation (33-40% of abandoners)
- Unexpected shipping costs discovered (60-70% of abandoners)
- Preference to use another channel
- Comparison shopping in progress
- Concerns about trust/security
- Payment method issues
- Technical problems during checkout

Only a subset of abandoners (estimates: 15-30%) actually abandon due to distraction alone.

**b) Mechanism Assumptions Not Validated**
- Assumes users will actually see/engage with push notification
- Assumes notification will effectively jog memory
- Ignores potential annoyance/unsubscribe effects
- Doesn't account for push notification fatigue on mobile

---

### 3. EFFECT SIZE EVALUATION
**Score: 2/10 - IMPLAUSIBLY HIGH**

### This is the Most Problematic Component

A 25% increase in completed orders from a single push notification is extraordinarily high. Here's why:

**Benchmarking Against Industry Data:**

| Intervention Type | Typical Effect Size | Expected Range |
|---|---|---|
| Email reminder (general) | 5-15% | Depends on audience quality |
| SMS reminder | 8-20% | Higher engagement than email |
| Retargeting ads (display) | 2-8% | Broader audience, lower relevance |
| Push notification reminders | 5-12% | Based on documented case studies |
| **Your Hypothesis** | **25%** | **Extremely high** |

**Why 25% is Implausible:**

1. **Population Heterogeneity**: A 25% uplift assumes the intervention works equally well on:
   - Users who abandoned due to price concerns (unlikely to be influenced by a reminder)
   - Users who abandoned due to trust concerns (reminder doesn't address)
   - Users actively shopping elsewhere (reminder is late)
   - Users who genuinely changed their mind (could work)

   In reality, you'd expect the effect to be concentrated in maybe 15-25% of abandoners (pure distraction/forgetfulness cases), not across the entire population.

2. **Statistical Precedent**:
   - Amazon's famous abandoned cart email (1997) showed ~0.5-1% recovery
   - Modern high-performing cart reminder campaigns: 5-12% recovery
   - The best-performing notification campaigns in e-commerce: 8-15%
   - To achieve 25%, you'd need nearly 2x the effect of best-in-class interventions

3. **Ceiling Effects**:
   - If you're already converting 70% of would-be customers to completed orders (before abandonment), you can't recover 25% of the remaining 30%
   - Mobile users already have 20-30% lower conversion rates; a single notification can't overcome that gap in one shot

4. **Diminishing Returns**:
   - Users who abandoned and come back naturally likely do so within hours (first wave)
   - A 1-hour push catches reconsiderers but not the "comparison shopping" or "price sensitive" cohorts
   - Multiple notification campaigns show diminishing returns; a single notification is limited

---

### 4. SCOPE & SPECIFICITY ISSUES
**Score: 3/10 - Dangerously Vague**

**What's Missing:**

1. **User Segmentation**
   - "All mobile users" is too broad
   - Should segment by: order value, product category, abandonment reason (if detectable), repeat vs. new customers
   - High-value orders may have different psychology than low-value ones
   - A $10 order reminder might annoy more than a $100 order reminder helps

2. **Treatment Specification**
   - What does the notification say? (tone affects response)
   - Does it include incentive (discount code)? This would confound results
   - Will it include product image, price, urgency language?
   - Is there a CTA button or link?
   - Notification content is crucial but completely unspecified

3. **Control Group Definition**
   - 100% exclusion from reminders? Or existing email reminders continue?
   - If you run push notifications but users already receive email reminders, you won't know which channel is responsible

4. **Success Metric Definition**
   - Completed orders = only previously-abandoned ones that were completed? Or all orders by experimental group?
   - Timeframe: measure for 24 hours? 7 days? 30 days?
   - What about repeat abandonment? (user receives push, ignores it, abandons again)

---

### 5. CONFOUNDING FACTORS & RISKS
**Score: 4/10 - Multiple Unaddressed Risks**

**Key Confounders Not Mentioned:**

1. **Seasonality**: When is this test running? Holiday season vs. off-season dramatically changes abandonment behavior

2. **Selection Bias**: Are you treating all abandoners equally?
   - Users who push notification-enable are likely different from those who disable
   - High-value customers may have different notification engagement than impulse buyers

3. **Notification Fatigue**:
   - If users already receive multiple notifications, adding another may decrease engagement across the board
   - Risk of unsubscribe increases

4. **Attribution Issues**:
   - How do you know the order was completed *because of* the push vs. user coming back anyway?
   - Users may have set a reminder for themselves
   - May have received notification from another channel simultaneously

5. **Negative Effects Not Considered**:
   - Increased unsubscribe rate from push notifications
   - Decreased lifetime value if users feel over-messaged
   - Potential reputational damage for "naggy" behavior

---

### 6. EXPERIMENTAL DESIGN READINESS
**Score: 3/10 - Missing Critical Details**

**What's Not Specified:**

- **Sample Size**: How many abandoners needed? No power analysis
- **Duration**: How long should the test run? (need to account for time to complete order post-push)
- **Randomization Method**: How will control/treatment be assigned? Random sampling by user? By session?
- **Guardrail Metrics**: What would make you stop the test? (e.g., unsubscribe rate > 5%?)
- **Secondary Metrics**: Push notification engagement rate, time-to-completion, average order value changes, repeat purchase rate
- **Data Infrastructure**: How will you track that a push notification was sent, received, and which order completion followed?

---

### 7. BUSINESS CASE ASSESSMENT
**Score: 6/10 - Reasonable but Over-optimistic**

**If 25% Effect Were Achievable** (it's not):
- Excellent ROI (push notification cost is minimal)
- Would be a major growth lever
- Would justify immediate rollout

**Realistic 8-12% Effect** (if hypothesis is refined):
- Still excellent ROI
- Worth testing
- Worth implementing if successful

**The Problem**:
You're using the 25% figure as justification without data. This inflates expected value and may lead to poor resource allocation.

---

## Critical Recommendations Before Experimentation

### MUST FIX (Blocking Issues):

1. **Revise Effect Size Hypothesis**
   - Change to: "We expect a 10-15% increase in completed orders"
   - Justify this against industry benchmarks
   - Provide confidence interval, not single point estimate

2. **Define Abandonment More Precisely**
   - Exactly when does abandonment occur? (e.g., cart item remains after 5 minutes of inactivity + user leaves the app)
   - What's the lookback window? (past 24 hours? 7 days?)

3. **Specify the Notification Content**
   - Write out the exact message users will see
   - Specify incentive (if any) to avoid confounding
   - This is critical—notification tone dramatically affects results

4. **Segment the Audience**
   - Don't test "all mobile users"
   - Start with: high-value orders (e.g., $50+) or specific product categories
   - This will likely show higher effect sizes and cleaner data

5. **Define Success Metrics Precisely**
   - "Completed orders" → "Users who received push notification and completed a previously-abandoned order within 24 hours"
   - Include guardrail metrics: unsubscribe rate, repeat abandonment rate, lifetime value

### SHOULD FIX (Important):

6. **Add Secondary Metrics**
   - Push notification delivery rate
   - Push notification engagement (open/click rate)
   - Time-to-completion after push
   - Whether completed order is same items or different items
   - Repeat purchase rate in next 30 days (to check for lifetime value impact)

7. **Establish Exclusion Criteria**
   - Don't message users already receiving other reminders
   - Consider frequency caps (don't re-push after 24 hours if not engaged)
   - Consider excluding users who've previously unsubscribed from notifications

8. **Plan for Heterogeneous Effects**
   - Prepare to analyze separately: new vs. returning customers, high vs. low order value, device type
   - The 1-hour timing may work very differently across segments

---

## Hypothesis Quality Scorecard

| Dimension | Score | Status |
|---|---|---|
| Clarity | 6/10 | Adequate |
| Mechanistic Reasoning | 5/10 | Weak |
| Effect Size Credibility | 2/10 | **CRITICAL** |
| Scope Definition | 3/10 | Incomplete |
| Confounding Awareness | 4/10 | Poor |
| Experimental Readiness | 3/10 | Not Ready |
| Business Relevance | 6/10 | Good |
| **OVERALL** | **4.2/10** | **NOT READY** |

---

## Final Verdict

### Recommendation: DO NOT EXPERIMENT YET

**Why:**
1. The 25% effect size is not evidence-based and will create false expectations
2. The hypothesis lacks specificity in key areas (notification content, success metrics, audience segmentation)
3. Mechanistic reasoning oversimplifies abandonment drivers
4. No details on experimental design (sample size, duration, randomization)

### Path Forward:

**Phase 1: Hypothesis Refinement (2-3 weeks)**
- Research: What % of cart abandoners cite forgetfulness as reason?
- Segment: Identify best segment to test (likely high-value orders)
- Revise: New hypothesis with 10-12% expected effect
- Design: Specify notification content and metrics

**Phase 2: Pilot Test (1-2 weeks)**
- Run small test with refined hypothesis
- Primary goal: directional signal and mechanism validation
- Don't expect 25%; be pleased with 8-12%

**Phase 3: Scale (if successful)**
- Roll out to broader audience
- Optimize notification timing and content based on pilot results
- Monitor for unsubscribe/fatigue effects

---

## Summary for Stakeholders

**The core idea is sound:** Reminding users about abandoned carts can drive conversions. However:

- **The 25% effect is implausible** (expect 8-12% max based on industry standards)
- **The hypothesis is under-specified** (notification content, metrics, segments undefined)
- **Not ready for experimentation** without substantial refinement

Invest time in hypothesis design now to avoid wasted experiment cycles later. A well-designed test with realistic expectations (10-15% effect) is far more valuable than a poorly designed test chasing implausible numbers.
