# Pricing Page Redesign — Sample Size Estimation

You've provided a solid input set. Let me estimate the required sample size and timeline.

## Inputs provided
- Metric: purchase conversion rate (binomial, conversion-style)
- Baseline conversion: 3.2%
- Minimum detectable effect: +0.4 percentage points (absolute)
- Target conversion: 3.6% (3.2% + 0.4%)
- Confidence level: 95% (two-tailed)
- Power: 80%

## Assumptions
- Using standard z-values for 95% confidence (z_α/2 = 1.96) and 80% power (z_β = 0.84)
- Two-variant test (control vs. redesign)
- No multi-arm correction needed

## Calculation

Using the conversion rate formula:
```
n_per_group = (z_α/2 + z_β)² × (p1×(1−p1) + p2×(1−p2)) / (p2 − p1)²
```

Where:
- (1.96 + 0.84)² = (2.80)² = 7.84
- p1 = 0.032, p2 = 0.036
- p1×(1−p1) = 0.032 × 0.968 = 0.030976
- p2×(1−p2) = 0.036 × 0.964 = 0.034704
- Sum of variance terms = 0.030976 + 0.034704 = 0.06568
- (p2 − p1)² = (0.004)² = 0.000016

**Numerator:** 7.84 × 0.06568 = 0.5153
**Denominator:** 0.000016
**n per group:** 0.5153 / 0.000016 ≈ **32,188 users per variant**
**Total sample size:** 32,188 × 2 = **64,376 users**

## Estimated duration

I cannot estimate how long the test will run without knowing your eligible traffic.

To complete the timeline, I need:
- **How many users visit your pricing page per week?** (or per relevant period)
- This should be the count of users actually eligible for the experiment, not total site traffic.

Once you provide eligible weekly traffic, I can calculate:
- Duration = 64,376 / (eligible users per week)

## Feasibility consideration

With a baseline of 3.2% and MDE of +0.4pp (a 12.5% relative uplift), the required sample is moderate-to-large. Whether this is practical depends on your traffic volume. If you have 10,000 eligible users/week, the test would run ~6.5 weeks. If traffic is lower, the timeline may extend significantly.
