# Subscription Plans and Revenue Lost to Churn

Which subscription plan loses the most revenue to churn, and what share of the total does each plan account for?

## Analyses
- [Subscription plan notebook](../notebooks/06_subscription_revenue_leak_analysis.ipynb)
  - Churn rate and spend by plan
  - Zero-spend customer profile
  - Linear regression: does spend differ by plan?
  - Monthly revenue lost to churn by plan
- [Executive summary](../reports/executive_summary_subscription.md)

## Key Finding
    Plus accounts for the largest share of monthly revenue lost to churn (39%) despite having the lowest churn rate. Basic has the highest churn rate but the smallest loss share (25%).

## Project Limitation
    Single snapshot per customer; zero-spend customers are excluded from revenue figures. See the executive summary for details.

## Environment
See the [project README](../README.md#environment).