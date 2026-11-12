# Spending and Customer Loyalty

    Are higher-spending customers more likely to stay, and is spend just a proxy for subscription plan?

## Deliverables
- [Analysis notebook](customer_loyalty_analysis.ipynb): spend and churn by plan, hypothesis tests (isolated and plan-controlled logistic regression)
- [Executive summary](executive_summary.md): findings and recommendation for a non-technical reader
- [Charts](./images): average and total revenue by plan and churn status, churn probability vs. spend

## Key Finding
    Higher spend is associated with lower churn, and the association remains after accounting for subscription plan: each extra $10 of monthly spend goes with about 5.7% lower odds of churn.

## Project Limitation
    Single snapshot per customer, so results show association, not cause. Lower spend may be a result of churn, and zero-spend customers are excluded.

## Environment
See the [project README](../README.md#environment).