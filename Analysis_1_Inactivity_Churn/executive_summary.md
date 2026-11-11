# Executive Summary: Inactivity and Churn

## Question
    How does churn change with days since a customer's last login, and where does the risk rise the most?

Findings| |
---|---
**_Key Findings_**<br><br>- Churn rises with inactivity, from [59.4]% at 0–30 days to [91.8]% at 150–180 days.<br><br>- The largest jump is between [60 and 90] days (+[9] points).<br><br>- The relationship is statistically significant at every inactivity level (p < 0.05), also after accounting for region, gender, and payment method.<br><br>- Churn is already [59.4]% among recently active customers, so inactivity alone does not identify who will leave.|<img src=images/churn_rate_by_days_since_last_login.png><img src=images/inference_logit_result.png>

## Recommendation
    Consider a retention outreach at [30 or 60] days of inactivity. A trigger at 30 days would reach [59.4]% of customers and cover [91.8]% of churners; a trigger at 60 days would reach [59.4]% and cover [91.8]%.

## Limitations
- The data is a single snapshot, so it shows association, not cause or timing.
- Inactivity may be partly a result of churn, since customers who leave stop logging in.
- Churn rates are high across all groups, so results may not generalize to other businesses.

## Details
See the [full analysis notebook](inactivity_churn_analysis.ipynb) for the statistical tests and methods.