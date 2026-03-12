# E-Commerce Recommendation Layout Test — Analysis

## Statistical Significance ≠ Practical Significance: Do Not Ship

Your experiment has reached statistical significance (p=0.031), but this is a textbook case where statistical significance masks a practically negligible effect. Here's the breakdown:

## The Math vs. Reality Gap

- **Observed effect:** +0.015 percentage points (+0.18% relative)
- **Pre-defined MDE:** +0.5 percentage points
- **The observed effect is 33× smaller** than your pre-defined threshold for business meaningfulness

Statistical significance here is a red herring driven by your massive sample size (500k per group). With 1 million users tested, even trivial improvements will achieve p<0.05. Your 95% confidence interval (+0.001pp to +0.029pp) captures a range that is entirely below your MDE, confirming this is noise, not signal.

## Why Sample Size Matters

Large sample sizes increase statistical power—they can detect tiny effects. But detection ≠ importance. Your layout change moved 7.5 additional users per 500,000 to cart. That's below the level where it justifies engineering effort, rollout risk, or opportunity cost.

## Guardrails Check

Good news—load time and revenue stayed flat. No collateral damage. But there's no collateral benefit either.

## Recommendation

**Do not ship.** The result is statistically significant but practically below threshold. Return to design—either increase the magnitude of the layout change or test a different hypothesis. This is a neutral-to-negative finding dressed up in p-values.
