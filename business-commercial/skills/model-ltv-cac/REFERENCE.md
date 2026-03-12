# Reference: Model LTV:CAC

## Why this reference exists

This skill is calculation-aware.

Its job is not to produce plausible-sounding unit economics numbers.
Its job is to calculate and interpret the LTV:CAC ratio from real inputs, and to flag when inputs are missing, assumptions are weak, or conclusions drawn from the ratio don't follow.

This reference defines:
- required inputs
- calculation formulas
- interpretation rules
- benchmarks
- invalid-use conditions
- behavioral rules under missing or misused inputs

---

## Core principle

LTV:CAC is only as accurate as the churn and margin assumptions underneath it.

If churn is optimistic, LTV is inflated.
If CAC excludes sales or support costs, it's understated.
A high ratio on weak inputs gives false confidence.

Do not produce a ratio without stating the assumptions it depends on.

---

## Mandatory inputs

Minimum required for LTV calculation:
- Average revenue per unit of time (monthly or annual, per customer)
- Gross margin percentage
- Churn rate (monthly or annual)

Required for CAC calculation:
- Total sales and marketing spend in a period
- Number of new customers acquired in the same period

Additional useful inputs:
- CAC by channel (blended CAC hides channel-level economics)
- LTV by customer segment or cohort (blended LTV hides segment variance)

---

## LTV formula

For subscription or recurring revenue models:

```
LTV = (ARPU × Gross Margin) / Churn Rate
```

Where:
- ARPU = average revenue per customer per period (monthly or annual)
- Gross Margin = revenue minus cost of goods sold, as a percentage
- Churn Rate = the fraction of customers lost per period (use the same time unit as ARPU)

Example (monthly):
- ARPU: $15/month
- Gross margin: 68%
- Monthly churn: 3.5%
- LTV = ($15 × 0.68) / 0.035 = $10.20 / 0.035 = $291

Example (annual, using annual time units directly):
- Annual contract value: $480
- Gross margin: 75%
- Annual churn: 18%
- LTV = ($480 × 0.75) / 0.18 = $360 / 0.18 = $2,000

Note: Do not convert annual churn to monthly by dividing by 12. That gives 1.5%, which is wrong (correct monthly churn from 18% annual is 1 - (1 - 0.18)^(1/12) ≈ 1.64%). When using a monthly ARPU, convert using the compound formula. When using annual ARPU, use annual churn directly. Both time units give the same result when kept consistent.

---

## CAC formula

```
CAC = Total Sales and Marketing Spend / New Customers Acquired
```

Do not exclude:
- Salaries for sales, marketing, and customer success (if CS is involved in acquisition)
- Agency fees and contractor costs
- Marketing tooling costs attributable to acquisition

Commonly mis-excluded costs that understate CAC:
- Salesperson base salaries (not just commissions)
- Content or SEO investment
- Trial/demo support costs

---

## LTV:CAC ratio

```
LTV:CAC ratio = LTV / CAC
```

Benchmark interpretation:
- Below 1x: acquiring customers costs more than their gross profit contribution. Unsustainable.
- 1x–2x: marginal. Business is barely recovering CAC, limited growth capital.
- 3x: commonly cited minimum threshold for sustainable growth investment
- 3x–5x: healthy
- 5x–10x: strong
- Above 10x: strong unit economics but may indicate underinvestment in growth; worth testing higher spend before concluding the model is perfectly efficient

A ratio above 10x combined with slow growth warrants checking whether the team is leaving growth on the table.

---

## Payback period

```
Payback period = CAC / (ARPU × Gross Margin)
```

This is the number of periods (months or years) required to recover the CAC from gross profit.

Benchmark interpretation:
- Under 12 months: strong for B2C subscription
- 12–18 months: acceptable for B2B SaaS with low churn
- 18–24 months: workable if churn is low and NRR > 100%
- Over 24 months: creates significant cash flow risk at scale; growth is cash-intensive

---

## Churn considerations

Churn is the most sensitive input in LTV.

### Monthly vs. annual churn
Always use consistent time units. Monthly and annual churn cannot be mixed without conversion.

Approximate conversion (not exact, but close for rates below 15%):
```
Annual churn ≈ 1 - (1 - Monthly churn)^12
```
Or in reverse:
```
Monthly churn ≈ 1 - (1 - Annual churn)^(1/12)
```

### Cohort-based churn vs. simple average
Simple average churn (total churned / total customers) is misleading for growing companies with a large share of new customers. New cohorts often churn faster than mature cohorts.

If churn data is available by cohort, use it.
If only a single churn rate is available, state it explicitly and flag that it may overstate or understate LTV depending on cohort behavior.

### Constant churn assumption
The standard LTV formula assumes constant monthly churn. This is often wrong:
- Real products typically have high early churn and lower late churn (surviving cohorts are self-selected)
- Using a simple average understates LTV for products with improving cohort retention

When this assumption is likely to produce an inaccurate result, say so.

---

## Gross margin considerations

LTV must use gross margin, not revenue.

Gross margin = (Revenue - Cost of Goods Sold) / Revenue

Commonly missed costs that reduce gross margin:
- Cloud infrastructure costs per customer
- Payment processing fees (2.5–3% for consumer, higher for international)
- Customer support costs directly tied to serving customers (not just acquisition)
- Third-party API costs per usage

If gross margin is unknown, the LTV calculation is incomplete. Do not substitute 100% margin as a simplification.

---

## Channel-level CAC

Blended CAC hides channel economics.

If CAC by channel is available:
- Calculate LTV:CAC ratio per channel
- Identify channels below 3x (potential budget reallocation)
- Identify channels above 8x (potential underinvestment)

If CAC by channel is not available, flag this as a gap. Blended CAC can mask a situation where paid acquisition is destroying value while organic acquisition inflates the average.

---

## Invalid-use conditions

The calculation is incomplete or misleading if:
- Churn rate is missing
- Gross margin is missing or assumed to be 100%
- CAC excludes significant non-advertising S&M costs (salaries, tools)
- LTV formula mixes monthly and annual time units without conversion
- A high LTV:CAC ratio is used to justify unlimited scaling without testing CAC curve behavior at higher spend

---

## Output expectations

A complete output includes:
- LTV with formula and all inputs stated
- CAC with formula and all inputs stated
- LTV:CAC ratio with benchmark comparison
- Payback period
- Key assumptions identified
- Interpretation: healthy / marginal / unsustainable
- Top improvement levers
- Sensitivity note: which input change would most affect the ratio?

---

## Behavioral rules under missing inputs

If churn is missing:
- State LTV cannot be calculated without it
- Offer scenario ranges tied to labeled churn assumptions
- Do not pick a default churn rate and proceed as if it's fact

If gross margin is missing:
- State LTV cannot be calculated without it
- Offer illustrative scenarios at 60%, 70%, 80% margin with explicit labels

If CAC by channel is missing:
- Calculate blended CAC only
- Flag that blended CAC may hide channel-level economics problems
- Recommend the team break it out before making channel investment decisions

---

## Relationship to adjacent skills

LTV:CAC should come before or alongside:
- analyze-unit-economics (LTV:CAC is a key output of unit economics)
- build-business-case (LTV:CAC grounds investment cases)
- strategize-channel-campaigns (CAC by channel feeds channel decisions)
- run-forecasting-scenarios (LTV:CAC assumptions feed growth forecasts)
