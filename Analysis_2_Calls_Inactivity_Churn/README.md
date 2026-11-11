# Customer Service Calls and Churn

A behavioral analysis of how churn changes with the number of customer service calls, with and without accounting for inactivity.

## Project Questions
- Do customer service calls signal frustration or engagement?
- At how many calls should a customer be escalated to retention outreach?
- Do calls matter on their own, or do they overlap with inactivity?

## Project Limitation
This is a single snapshot per customer, so results show association, not cause or timing. Customers may call because they are about to cancel, so call count may be a result of churn and not only a signal.

## Analyses
- [Calls vs. churn notebook](../notebooks/03_calls_inactivity_churn_analysis.ipynb)
  - Churn rate by number of calls
  - Logistic regression with calls alone
  - Logistic regression controlling for inactivity (likelihood-ratio test)
  - Estimated annual revenue lost by call group
- [Executive summary](../reports/executive_summary_calls.md)

## Key Finding
Churn rises from 64.6% at 0 calls to 94.8% at 6+ calls, and the association remains after accounting for inactivity.

## Environment
See the [project README](../README.md#environment).