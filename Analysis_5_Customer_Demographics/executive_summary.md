# Executive Summary: Customer Demographics and Churn

## Question
    Are region, payment method, age, or gender associated with customer churn?

## Key Findings
- **Only region is associated with churn** ($\chi^2$ = 32.95, df = 3, p < 0.001). Gender (p = 0.98), age (p = 0.74), and payment method (p = 0.07, borderline) show no statistically significant association.
- **Region stays significant after accounting for** monthly spend, support calls, inactivity, and age (likelihood-ratio test: 47.48, df = 3, p < 0.001, 8,168 customers).
- **The effect is very weak.** Cramér's V is 0.066, indicating that region have a very low power of separating churners from non-churners
- **Churn is high in every region**, at 71.5% or more.


#### **_Unadjusted Churn Rate_**
| Region | Churn rate | Difference vs. East | Odds ratio vs. East |
|---|---|---|---|
| East | 71.5% | n/a | 1.00 |
| North | 75.6% | +4.1 pts | 1.24 |
| West | 77.1% | +5.6 pts | 1.34 |
| South | 79.1% | +7.7 pts | 1.52 |

## Recommendation
    Demographic attributes are weak signals for churn and a poor basis for customer retention.

## Limitations
- The data is a single snapshot, so it shows association, not cause.
- Only four demographic variables were tested.
- Churn is unusually high in every group, and the data source is unknown, so results may not generalize.
- About a quarter of customers were excluded because of missing values (mainly age): roughly 7,600 of 10,300 remain for the chi-squared tests, and 8,168 for the controlled test.
- No external data is available to validate the records.

## Details
See the [full analysis notebook](customer_demographics_and_spending.ipynb).