# A/B Test Duration Estimate: SaaS Trial Expiry Email

## Executive Summary

**Cannot provide a precise duration without defining the Minimum Detectable Effect (MDE).** However, based on your volume and typical business scenarios, your test will likely run **1-3 weeks** depending on the magnitude of improvement you're testing for.

## Given Information

- **Baseline conversion rate:** 12.3%
- **Weekly email volume:** 4,500 trial expiry emails
- **Test type:** Two-sample proportion test (control vs. treatment)

## Missing Critical Input

To calculate exact test duration, you need to define:

**Minimum Detectable Effect (MDE):** What percentage conversion lift would justify implementing the new email design?

Common questions to help define this:
- What's the dollar impact of a 5% lift in trial-to-paid conversion?
- How much effort/cost is required to maintain the new design?
- Is this a critical business metric or a minor optimization?

## Scenario Analysis (95% Confidence, 80% Power)

### Scenario 1: 15% Relative Lift
- **New conversion rate:** 14.1% (from 12.3%)
- **Sample size per group:** 5,285
- **Total sample size needed:** 10,571
- **Duration:** **2-3 weeks**

### Scenario 2: 20% Relative Lift
- **New conversion rate:** 14.8% (from 12.3%)
- **Sample size per group:** 3,031
- **Total sample size needed:** 6,063
- **Duration:** **1-2 weeks**

### Scenario 3: 25% Relative Lift
- **New conversion rate:** 15.4% (from 12.3%)
- **Sample size per group:** 1,977
- **Total sample size needed:** 3,954
- **Duration:** **~1 week**

## Statistical Framework

### Standard Parameters Used
- **Confidence level:** 95% (α = 0.05, two-tailed)
- **Statistical power:** 80% (β = 0.20)
- **Z-score for confidence:** 1.96
- **Z-score for power:** 0.84

### Sample Size Formula
```
n = 2 × (z_α + z_β)² × p̄ × (1 - p̄) / (p₁ - p₂)²
```

Where:
- p̄ = pooled proportion (average of control and treatment conversion rates)
- p₁, p₂ = conversion rates for control and treatment groups
- n = sample size per group

## Key Considerations

### 1. Why Statistical Power Matters
- **80% power** (industry standard) means there's an 80% chance of detecting a true effect of the size you're testing for
- If you want higher confidence, use **90% power**, which requires ~20% more samples and thus ~1 week longer
- Trade-off: higher power = longer test, but better protection against missing real effects

### 2. Revenue Impact Math
With 4,500 emails/week:
- **Even a 5% lift** = ~23 additional conversions per week
- At typical SaaS LTV values ($500-2,000+), this could be $11K-$46K+ per week
- At 3-week test duration: $33K-$138K+ revenue impact

### 3. Test Validity Assumptions
- ✓ Consistent weekly email volume (~4,500/week)
- ✓ Random assignment to control/treatment groups
- ✓ No external factors skewing results during test period
- ✓ Single metric being tested (if testing multiple variants, adjust alpha)

### 4. Sequential Testing Alternative
If you can't wait 2-3 weeks:
- Sequential testing allows you to check results daily and stop early if effect is strong
- Requires more sophisticated analysis (e.g., Bayesian methods)
- Popular for high-velocity experiments but requires careful setup

## Recommendations

1. **Define Your MDE:**
   - Calculate the revenue impact per percentage point of conversion lift
   - Work with product/business teams to determine the minimum worthwhile improvement
   - Even modest lifts can be valuable at your scale

2. **Choose Your Power Level:**
   - **80% power:** Faster (1-3 weeks), acceptable for most features
   - **90% power:** More rigorous, takes ~20% longer, for critical decisions

3. **Plan for Seasonality:**
   - Check if trial expiry rates vary by day of week or season
   - If so, consider running through full weeks/cycles to avoid bias

4. **Set Success Criteria Before Launch:**
   - Define what result = "definitely roll out" vs. "needs more investigation"
   - Avoid p-hacking by pre-registering your statistical test

## Quick Reference

| Relative Lift | Duration | Impact (at 5% LTV)* |
|---|---|---|
| 15% (12.3% → 14.1%) | 2-3 weeks | $33K-$138K |
| 20% (12.3% → 14.8%) | 1-2 weeks | $22K-$92K |
| 25% (12.3% → 15.4%) | ~1 week | $11K-$46K |

*Based on 4,500 emails/week at varying SaaS LTV values ($500-$2,000+)

## Conclusion

**Most likely timeline: Run for 2 weeks** if you're testing for a reasonable (15-20%) relative lift. This balances statistical rigor with practical business needs and should capture a meaningful sample (6,000-10,500 total observations).

If the new design is lower-effort to maintain, testing for even 15% lift is reasonable. If it requires significant resources, consider raising your MDE threshold to 25%+ to justify the investment.
