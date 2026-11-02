# Subscription Plan Analysis: Identifying Subscription Plan with the Highest Risk and Revenue Loss Share

## Overview
    This project analyze the dataset to determine the attrition per subscription plan and determine the revenue loss and percent loss due to customer churns. The project includes a linear regression model to determine if the revenue vary across all subscription plan.

## Question
* Which subscription plans are the leakiest, and are they worth saving?

## Results
| | |
---|---
**_Initial Findings_**<br>Retained customers spends more than churned customers<br><br>**_Hypothesis Testing_**<br>The results shows that there is a significant relationship between `monthly_spend` and `subscription_plan`, which indicates that revenue vary across all tiers.<br><br>**_Analysis Results_**<br>_Zero Spenders_<br>Zero spenders are customer who haven't paid any amount. Majority of zero spenders are in `Basic` plan and are equally distributed across all regions, while few are in the `Pro` plan.<br>Results also shows that almost all of the zero spenders are already churned and 75% are already inactive for more than 30 days across all subscription plan and region.<br><br>**_Non Zero Spenders_**<br>Basic plan have the lowest revenue with $45, followed by Pro plan with $40 more than Basic or $85 in total, then Plus plan with the highest average monthly revenue of $110 more than Basic plan or $150 in total.<br><br>**_Monthly Total Loss_**<br>Plus is the leakiest plan with a total share loss of 39%, generating a total loss of $204k from churned customers. Pro plan on the other hand have a total share loss of 36% and a total generated loss of $189k from churned customers.|![alt text](images/image-1.png)![alt text](images/image.png)![alt text](images/image-2.png)![alt text](images/image-3.png)
