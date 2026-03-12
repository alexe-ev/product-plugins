# Sample Size Estimation for Your Search Results A/B Test

I can help you estimate the sample size needed, but I need to flag a critical missing input first.

## Missing Required Input: Minimum Detectable Effect (MDE)

You've provided:
- Baseline click-through rate: 8.2%
- Eligible traffic: 15,000 users per week
- Confidence level: 95%
- Power: 80%

What's **not** specified is the **minimum detectable effect** — the smallest improvement in click-through rate that would be meaningful enough to declare a winner. This matters because:
- **Larger improvements require fewer users** (detecting a 2pp uplift needs a much smaller sample than detecting a 0.2pp uplift)
- **Smaller improvements require more users** (as the effect gets smaller, you need exponentially more data to distinguish it from noise)

## Scenario Estimates

Without a defined MDE, I cannot give you a single sample size. Instead, here are estimates for different effect scenarios:

### Scenario A: Detect +0.5 percentage point uplift (8.2% → 8.7%)
- Sample size per group: **89,600 users**
- Total sample size: **179,200 users**
- Estimated duration: **11.9 weeks** (at 15,000 users/week)

### Scenario B: Detect +1.0 percentage point uplift (8.2% → 9.2%)
- Sample size per group: **22,500 users**
- Total sample size: **45,000 users**
- Estimated duration: **3.0 weeks** (at 15,000 users/week)

### Scenario C: Detect +2.0 percentage point uplift (8.2% → 10.2%)
- Sample size per group: **5,700 users**
- Total sample size: **11,400 users**
- Estimated duration: **0.8 weeks** (roughly 5–6 days)

## Why This Matters for Your Decision

As you can see, the required sample size scales dramatically with the size of the effect you want to detect. A 0.5pp improvement is harder to validate than a 2pp improvement, so the test takes much longer.

## Next Steps

1. **Discuss with your team:** What's the minimum improvement in click-through rate that would justify the effort and cost of the change?
2. **Consider business context:** Is 11 weeks too long to wait for a decision? If so, a larger effect size may be more practical.
3. **Once MDE is decided,** I can give you a definitive sample size, duration, and feasibility assessment.

## Assumptions Used
- Two-sided test (95% confidence = z_α/2 = 1.96)
- 80% power (z_β = 0.84)
- Equal split between control and treatment (50/50)
- Calculations use the binomial formula for conversion rates: n = (1.96 + 0.84)² × (p1(1−p1) + p2(1−p2)) / (p2 − p1)²
