## Input
We want to understand our LTV:CAC. We're a SaaS product. Average contract value is $480/year. We spend about $120k/month on sales and marketing and acquire around 200 new customers per month.

## Expected output
Status:
Partial inputs — LTV:CAC ratio cannot be calculated without churn rate and gross margin.

What can be calculated now:
CAC = Total S&M Spend / New Customers Acquired
CAC = $120,000 / 200 = $600

Annual contract value per customer: $480/year

What is missing for LTV:
- Gross margin: required to calculate gross profit per customer. LTV uses gross profit, not revenue. Without margin, LTV is overstated.
- Churn rate: required to estimate customer lifetime. At 0% annual churn, LTV = infinity. At 20% annual churn, average lifetime is 5 years. The range makes LTV meaningless without this number.

Rough LTV scenarios (illustrative, not a substitute for real data):

Assuming 70% gross margin and varying churn:
- 10% annual churn: LTV = ($480 × 0.70) / 0.10 = $3,360. LTV:CAC = 5.6x
- 15% annual churn: LTV = $336 / 0.15 = $2,240. LTV:CAC = 3.7x
- 25% annual churn: LTV = $336 / 0.25 = $1,344. LTV:CAC = 2.2x (marginal)

These are scenarios, not your actual ratio. The 15% annual churn scenario produces a ratio that is borderline acceptable (3.7x). At 25% churn, the model is marginal.

What must be provided to complete the analysis:
- Annual or monthly churn rate
- Gross margin percentage

Payback period (without churn dependency):
Payback = CAC / (ACV × Gross Margin assumption)
At 70% gross margin: $600 / ($480 × 0.70) = $600 / $336 = 1.8 years payback (21 months). This is high for a SaaS business — strong churn control is needed to make this work economically.

Recommended next inputs:
- Churn rate (annual or monthly customer retention rate)
- Gross margin (after cost of goods sold / service delivery costs)
