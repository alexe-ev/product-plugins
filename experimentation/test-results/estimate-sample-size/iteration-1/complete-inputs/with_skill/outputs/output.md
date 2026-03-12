# Sample Size Estimation: Food Delivery App A/B Test

## Experiment Summary
Testing a new restaurant card design to increase click-to-order conversion rate on a food delivery app.

## Sample Size Estimate

### Sample size per group
Approximately **18,400 users**

### Total sample size
Approximately **36,800 users**

### Estimated duration
Approximately **1.05 weeks** (5.3–7.4 days depending on traffic distribution)

With 35,000 eligible users per week and a 50/50 split, the experiment would require roughly 1.05 weeks to reach the required sample size.

## Inputs Used
- Metric type: Conversion rate (click-to-order)
- Baseline conversion: 7.8%
- Target conversion: 8.6% (baseline + 0.8 percentage points)
- Minimum detectable effect: +0.8 percentage points (absolute)
- Confidence level: 95% (α = 0.05, two-tailed)
- Statistical power: 80% (β = 0.20)
- Eligible traffic: 35,000 users per week
- Split ratio: 50/50

## Calculation Details

### Formula
For a two-proportion fixed-horizon A/B test:

```
n = (Z_α/2 + Z_β)² × (p₁(1-p₁) + p₂(1-p₂)) / (p₂ - p₁)²
```

### Parameters
- Z_α/2 = 1.96 (for 95% confidence, two-tailed)
- Z_β = 0.84 (for 80% power)
- p₁ (baseline) = 0.078
- p₂ (target) = 0.086
- p₂ - p₁ = 0.008

### Intermediate calculations
- (Z_α/2 + Z_β)² = (1.96 + 0.84)² = 7.84
- p₁(1-p₁) = 0.078 × 0.922 = 0.0719
- p₂(1-p₂) = 0.086 × 0.914 = 0.0786
- Numerator = 7.84 × (0.0719 + 0.0786) = 1.1785
- Denominator = 0.008² = 0.000064
- **Sample per group = 1.1785 / 0.000064 ≈ 18,414**
- **Total sample = 2 × 18,414 ≈ 36,828**

### Duration calculation
Duration = Total sample / Eligible traffic per period
Duration = 36,828 / 35,000 ≈ **1.05 weeks**

## Assumptions

1. **Two-variant fixed-horizon test**: The experiment compares control (current design) vs. treatment (new design) over a fixed period.

2. **Stable eligible traffic**: The 35,000 users/week figure represents eligible traffic that actually reaches the restaurant card step and is stable across the test period. No major fluctuations due to acquisition source shifts, campaign cycles, or seasonal changes.

3. **Independent observations**: Each user is counted once; no session-level or repeated measurement bias.

4. **No external confounds**: No major product launches, promotions, or competitive events interfere with the test period.

5. **Adequate conversion tracking**: Click-to-order events are properly tracked with no missing or misflagged data.

6. **Even split**: Traffic is split 50/50 between variants with no preference bias.

## Feasibility Assessment

**Status: Feasible**

### Positive factors
- The required sample size (36,828 users) is well within the available weekly traffic (35,000 users/week).
- The test can complete in approximately one week, allowing for rapid decision-making.
- The minimum detectable effect (0.8 percentage points absolute, ~10% relative uplift) is reasonable and achievable with a good design.

### Considerations
- **Traffic dependency**: If actual eligible traffic is lower than 35,000 users/week, duration will extend proportionally. Confirm that the 35,000 figure excludes ineligible or bot traffic.
- **Weekly seasonality**: Food delivery often shows day-of-week and time-of-day patterns. Consider running the test for full weeks (ideally 2 weeks) to absorb these patterns and avoid biased estimates.
- **Card design impact**: The 0.8 pp uplift is based on expected impact from the design change. If the team's confidence in the uplift is lower, consider revising the MDE or running a longer exploratory test.
- **External events**: During the test window, monitor for promotions, app outages, or other changes that could confound results.

## Risk and Caveats

1. **Traffic assumptions**: This estimate assumes that all 35,000 weekly users are equally eligible for assignment. If eligibility is segment-specific (e.g., only new users, only certain geographies), revise the eligible traffic figure.

2. **Conversion window**: If users are counted in conversion only after a delay (e.g., next day delivery confirmation), ensure the test period includes sufficient observation time post-assignment.

3. **Repeat users**: If the same user can see both variants across multiple sessions, adjust the sample size formula to account for dependency. This estimate treats each user-session as independent.

4. **Statistical power**: At 80% power, there is a 20% risk of a Type II error (false negative). If the true effect is at the MDE boundary, you have a 1-in-5 chance of not detecting it. To reduce this risk, increase power to 85% or 90% (which increases sample size).

## Recommendations

1. **Confirm traffic baseline**: Validate that 35,000 users/week is the eligible traffic that reaches the restaurant card step, not total app traffic.

2. **Run for full weeks**: If possible, run the test from Monday to Sunday (or align with your traffic cycle) to avoid day-of-week bias.

3. **Monitor key metrics**: During the test, track:
   - Click-to-order conversion rate in both arms
   - Sample ratio mismatch (SRM) for assignment bias
   - Day-over-day consistency to detect seasonality
   - Any external events or product changes

4. **Plan sequential analysis (optional)**: If a one-week timeline is critical, consider a sequential (continuous monitoring) approach instead of fixed-horizon. This allows earlier stopping if the effect is stronger than expected, but requires adjusted α and β.

5. **Prepare for low power scenarios**: If the true effect turns out to be smaller than 0.8 pp (e.g., 0.5 pp), the current sample may not be sufficient to detect it. Have a plan for extending the test or reframing the null hypothesis.

## Next Steps

1. Share this estimate with the experiment planning team.
2. Confirm eligible traffic figure and any segment constraints.
3. Validate the 0.8 pp MDE with product and design stakeholders.
4. Set a launch date and monitor the first few days for traffic stability.
5. Use this sample size in the experiment launch checklist (design-experiment-plan).
