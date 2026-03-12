# A/B Testing Metrics Guide

## Overview
An A/B test requires clear, measurable success metrics to determine whether a change (variant B) performs better than the control (variant A). Without specific context about your product or test, here are the key metric categories to consider.

## Primary Metric Types

### 1. Conversion Metrics
- **Conversion Rate**: Percentage of users who complete a desired action (e.g., purchase, signup, form submission)
- **Click-Through Rate (CTR)**: Percentage of users who click on a specific element
- **Completion Rate**: Percentage of users who finish a process or flow

### 2. Engagement Metrics
- **Time on Page/Session**: How long users spend interacting with the variant
- **Scroll Depth**: How far down the page users scroll
- **Feature Usage**: Frequency or percentage of users engaging with specific features
- **Return Rate**: Percentage of users who come back within a defined timeframe

### 3. Business Metrics
- **Revenue Per User (RPU)**: Average revenue generated per test participant
- **Average Order Value (AOV)**: Mean transaction value
- **Customer Lifetime Value (CLV)**: Total expected value from a customer
- **Cost Per Acquisition (CPA)**: Cost to acquire one customer through the variant

### 4. Quality/Experience Metrics
- **Bounce Rate**: Percentage of users who leave without taking action
- **Error Rate**: Frequency of technical issues or failed transactions
- **User Satisfaction**: NPS, CSAT, or other sentiment measures
- **Page Load Time**: Performance metric affecting user experience

## Key Principles for Selecting Metrics

1. **Align with Business Goals**: Choose metrics directly tied to what matters for your business (revenue, engagement, retention, etc.)

2. **Statistical Power**: Select metrics with sufficient expected variation to detect meaningful changes with reasonable sample sizes

3. **Directional Clarity**: Define whether higher or lower is better for each metric

4. **Avoid Vanity Metrics**: Prioritize metrics that reflect actual user value, not just volume (e.g., active returning users vs. total clicks)

5. **Sensitivity & Specificity**:
   - Sensitivity: The metric detects real effects when they exist
   - Specificity: The metric doesn't react to noise or external factors

## Primary vs. Secondary Metrics

- **Primary Metric**: The main KPI you're optimizing for (should be 1-3 maximum)
- **Secondary Metrics**: Supporting metrics that provide context and guard against negative side effects
- **Guardrail Metrics**: Metrics you must NOT harm (e.g., if testing checkout speed, don't sacrifice conversion rate)

## Sample Metric Selection Examples

### For an E-commerce Site:
- Primary: Conversion rate (purchases per visitor)
- Secondary: Average order value, cart abandonment rate
- Guardrail: Page load time, error rate

### For a SaaS Product:
- Primary: Feature adoption rate or DAU (Daily Active Users)
- Secondary: Time to value, feature engagement depth
- Guardrail: Churn rate, support ticket volume

### For Content/Media Platform:
- Primary: Session duration or return rate
- Secondary: Click-through rate, content discovery rate
- Guardrail: Bounce rate, ad load time

## Statistical Considerations

- **Sample Size**: Larger samples reduce the time needed to reach statistical significance
- **Minimum Detectable Effect (MDE)**: The smallest meaningful difference you want to detect
- **Confidence Level**: Typically 95% (alpha = 0.05)
- **Statistical Power**: Typically aim for 80% power
- **Run Duration**: Test long enough to capture weekly/seasonal patterns (typically 1-4 weeks)

## Common Pitfalls to Avoid

1. **Too Many Metrics**: Increases false positive risk (multiple comparison problem)
2. **Moving Goalposts**: Define metrics before running the test
3. **Peeking**: Don't check results before reaching the sample size target
4. **Ignoring Segments**: Analyze results by user segment when possible
5. **Correlation vs. Causation**: Remember that correlation in metrics doesn't prove causation

## Next Steps

To define metrics for your specific A/B test, consider:

1. What is the primary business objective?
2. What user action best measures success toward that goal?
3. What secondary metrics provide important context?
4. What metrics must we protect (guardrails)?
5. How much traffic/time do we have available?
6. What's the minimum change we care about detecting?

Once you answer these questions, you can select appropriate metrics and determine the required sample size using standard statistical power calculators.
