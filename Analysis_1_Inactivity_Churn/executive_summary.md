# Inactivity Churn Analysis : A Logistic Regression Analysis for Identifying Inactivity Churn Tendency

## Deliverables
- Target Variable Analysis
- Hypothesis testing
- Logistic Regression Analysis
- Executive Summary

## Question
    How quickly does inactivity turn into churn?
    Is there a threshold where risks jumps?

## Results
| | |
--|--
**_Initial Findings_**<br>Longer customer inactivity have a higher chance of churning and each 30 days interval increases the total churned by approx. 200 customers|![alt text](images/image.png)![alt text](images/image-1.png)<br>
**_Hypothesis Results_**<br><br>$H_0$ = The regression coefficient ($β_r$) = 0<br>Customer inactivity has no effect on the log-odds (probability) of customer churn<br>$H_1$ = The regression coefficient ($β_r$) != 0<br>Customer inactivity has effect on the log-odds (probability) of customer churn.<br><br>Customer inactivity shows a positive relationship with churn rate and is strongly significant for all intervals.<br><br>Inverse Transformation Results shows that a 90 days inactivity have the highest churn rate jump. Although 90 Days inactivity shows the highest jump, the baseline churn rate is already high. Therefore, setting the threshold to 30d is the ideal action.<br><br>All of the results rejects the null hypothesis, therefore, we can conclude that customer inactivity has a positive effect on the log-odds of customer churn|![alt text](images/image-2.png)![alt text](images/image-3.png)