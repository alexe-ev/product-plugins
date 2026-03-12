# Success Metrics Framework for Experiment

## Overview
This framework defines the key metrics needed to evaluate the success of an experiment. Without specific context about the experiment's goals, this provides a comprehensive template covering multiple dimensions of measurement.

## 1. Primary Success Metrics

### 1.1 Business Impact Metrics
- **Conversion Rate**: Percentage of participants who complete the desired action
- **Revenue Impact**: Change in revenue or transaction value attributed to the experiment
- **Customer Lifetime Value (CLV)**: Long-term value of customers exposed to the experiment
- **Return on Investment (ROI)**: Cost of the experiment vs. financial gains

### 1.2 User Engagement Metrics
- **Click-Through Rate (CTR)**: Percentage of users who interact with the variant
- **Time on Page/Feature**: Average duration users spend engaging with the experiment
- **Feature Adoption Rate**: Percentage of eligible users who use the new feature
- **Repeat Usage**: Frequency of users returning to use the feature

### 1.3 User Experience Metrics
- **User Satisfaction Score**: Post-interaction survey or NPS (Net Promoter Score)
- **Task Completion Rate**: Percentage of users who successfully complete intended actions
- **Error Rate**: Frequency of errors or unsuccessful interactions
- **User Effort Score**: Subjective measure of ease/difficulty in using the feature

## 2. Secondary Metrics (Health Metrics)

### 2.1 Technical Metrics
- **Page Load Time**: Speed of the feature or page variant
- **Error Rate**: Backend or client-side errors encountered
- **Availability/Uptime**: Percentage of time the feature functions properly
- **Performance Degradation**: Change in overall system performance

### 2.2 Quality Metrics
- **Bounce Rate**: Percentage of users who leave without taking action
- **Churn Rate**: Percentage of users who abandon the feature/product
- **Support Ticket Increase**: Change in customer support requests related to the feature
- **Bug Reports**: Number of issues reported by users

### 2.3 Data Quality Metrics
- **Sample Size**: Number of participants reaching statistical significance
- **Segment Representation**: Ensure all relevant user segments are represented
- **Data Completeness**: Percentage of valid, trackable events

## 3. Guardrail Metrics (What NOT to break)

- **Retention Rate**: Ensure we don't lose existing users
- **Core Engagement**: Ensure other features remain unaffected
- **Performance**: Ensure system speed doesn't degrade significantly
- **Error Rates**: Ensure no new critical errors are introduced
- **User Satisfaction**: Ensure overall satisfaction doesn't decline

## 4. Statistical Considerations

### 4.1 Power and Significance
- **Statistical Significance Level**: Typically p < 0.05
- **Statistical Power**: Typically 80% (beta = 0.2)
- **Minimum Detectable Effect (MDE)**: Smallest meaningful change to detect
- **Sample Size Required**: Calculated based on variance and MDE

### 4.2 Duration
- **Test Duration**: How long the test should run (days/weeks)
- **Sequential Testing**: Whether to use continuous monitoring or fixed endpoint
- **Seasonality Considerations**: Account for time-of-day or seasonal effects

## 5. Segmentation Metrics

Break down success metrics by:
- **User Segments**: New vs. returning users, user tier/cohort
- **Device Type**: Mobile, desktop, tablet
- **Geographic Region**: Different markets may respond differently
- **User Behavior Segment**: Power users vs. casual users

## 6. Directional vs. Directional Metrics

### Primary Directional Metrics (must improve)
- The core metric the experiment is designed to improve
- Should show clear positive direction

### Secondary Supporting Metrics (should not harm)
- Related metrics that provide context
- Should remain neutral or positive

## 7. Success Criteria Definition

### Metric Success Thresholds
For each primary metric, define:
- **Minimum Acceptable Effect**: The smallest improvement worth shipping
- **Expected Effect Size**: What we reasonably expect to see
- **Confidence Level**: Required certainty (95% is standard)

### Overall Success Decision
- **All Primary Metrics Positive**: Feature is successful
- **Mixed Results**: Requires qualitative analysis
- **Primary Metrics Negative**: Feature should not ship
- **Guardrails Violated**: Do not ship regardless of primary metrics

## 8. Monitoring and Evaluation Timeline

| Phase | Timeframe | Key Activities |
|-------|-----------|-----------------|
| Setup | Pre-launch | Finalize metrics, set tracking, power calculation |
| Launch | Day 1-7 | Monitor for technical issues, sanity checks |
| Early Results | Week 1-2 | Preliminary analysis, watch guardrails |
| Main Analysis | Week 2+ | Wait for statistical significance, segment analysis |
| Decision | End of test | Interpret results, make go/no-go decision |

## 9. Documentation Requirements

For each metric, document:
- **Definition**: Exact calculation method
- **Owner**: Who is responsible for tracking
- **Data Source**: Where the metric is collected
- **Tool/Dashboard**: Where to find the metric
- **Historical Baseline**: What is the current performance
- **Target**: What improvement would be meaningful

## 10. Common Pitfalls to Avoid

- Not defining metrics before the experiment starts
- Too many metrics (dilutes focus and increases false positives)
- Ignoring guardrail metrics
- Not accounting for multiple testing (p-hacking)
- Insufficient sample size or test duration
- Not segmenting by meaningful user populations
- Changing success criteria after seeing results
- Confusing correlation with causation

## 11. Post-Decision Actions

### If Successful
- Document learnings
- Plan rollout strategy
- Monitor metrics in production
- Communicate results to stakeholders

### If Not Successful
- Analyze why results fell short
- Consider variations or different approaches
- Document learnings for future experiments
- Plan next iteration if warranted

## 12. Example Metrics Template

For an actual experiment, populate this template:

| Metric | Baseline | Target | Calculation | Statistical Test |
|--------|----------|--------|-------------|------------------|
| [Primary 1] | [Current] | [Goal] | [Formula] | [Method] |
| [Primary 2] | [Current] | [Goal] | [Formula] | [Method] |
| [Guardrail 1] | [Current] | [Minimum] | [Formula] | [Method] |
| [Guardrail 2] | [Current] | [Minimum] | [Formula] | [Method] |

---

## Conclusion

This framework provides a comprehensive foundation for defining success metrics for any experiment. The specific metrics should be tailored to your experiment's context, business goals, and user base. Start with 2-4 primary metrics, add relevant guardrails, and support them with segment analysis for deeper insights.
