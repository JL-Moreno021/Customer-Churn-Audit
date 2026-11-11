# Project Overview

## Inactivity and Churn
    A behavioral analysis of how churn changes with the number of days since a customer's last login.

## Project Question
    How does the churn rate change with days since last login, and at which point does the risk rise the most?

## Project Limitation
    Days since last login measures customer engagement at the time the data was collected. It is a single snapshot per customer, so it cannot show how quickly customers churn.

    Inactivity may also be a result of churn, since customers who have left stop logging in. For this reason, it is analyzed as a behavioral variable associated with churn, not as a cause or a definitive measure of attrition.

## Analyses
- [Inactivity vs. churn notebook](inactivity_churn_analysis.ipynb)
  - Target variable and churn rate by inactivity group
  - Chi-squared test of independence
  - Likelihood-ratio (G²) test with controls for region, gender, and payment method
- [Executive summary](../reports/executive_summary.md)

## Key Finding
    Churn rises from 59.4% at 0–30 days to 91.8% at 150–180 days, with the largest jump between 60 and 90 days (+[9] points)

## Environment
See the [project README](../README.md#environment).