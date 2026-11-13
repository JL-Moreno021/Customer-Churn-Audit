# Churn Prediction Model

    Final stage of the customer churn project. It builds on the five analysis notebooks and asks whether the variables found to be associated with churn can predict it for individual customers.

## Question
    Can inactivity, support calls, spend, subscription plan, and region predict which customers churn, and how much better is the model than flagging every customer?

## Deliverables
- [Modeling notebook](project_model.ipynb): feature preparation, train/validation/test split, logistic regression and XGBoost comparison, evaluation

## Inputs from the Analyses
| Variable | Finding in the analyses | In the model? |
|---|---|---|
| `days_since_last_login` | Churn rises with inactivity | Yes |
| `customer_service_calls` | Churn rises with call count, also after accounting for inactivity | Yes |
| `monthly_spend` | Higher spend goes with lower churn, also after accounting for plan | Yes |
| `subscription_plan` | Plans differ in revenue lost to churn | Yes |
| `region` | Significant but very weak association (Cramér's V = 0.066) | Yes |
| `gender`, `payment_method`, `age` | No statistically significant association | No |
| `customer_id` | Identifier | No |

## Data
- Source: `customer_churn_clean.csv` (output of the data cleaning notebook), 10,300 customers.
- Target: `churn` (1 = churned, 0 = retained). 76.2% of training customers churned.
- Predictors (5): `region` and `subscription_plan` (one-hot encoded, one level dropped), `days_since_last_login`, `customer_service_calls`, `monthly_spend`.
- Missing values: `customer_service_calls` (52 rows, 0.5%) and `monthly_spend` (585 rows, 5.7%) are filled with the training-set median inside the pipeline. No rows were dropped.

## Method
- **Split:** stratified 60% train / 20% validation / 20% test (6,180 / 2,060 / 2,060 customers). The test set is split off first (`random_state=42`), then the validation set from the remainder (`random_state=0`).
- **Preprocessing:** median imputation and standardization for numeric columns, one-hot encoding for categorical columns, all fitted on training rows only.
- **Models:** logistic regression (`max_iter=1000`) and XGBoost (`binary:logistic`). XGBoost is tuned with `GridSearchCV` (5-fold stratified cross-validation, 324 parameter combinations, refit on F1).
- **Metrics:** ROC AUC score, plus precision, recall, F1, accuracy, and the share of customers flagged. Accuracy and F1 metrics are not for model performace as 3/4 of the records are churned customers, so predicting "churn" for everyone already scores well.
- **Baseline:** predict churn for every customer.

## Results
| | |
--|--
Logistic regression's 5-fold cross-validation ROC AUC on the training set is 0.744 (XGBoost: [0.735]).![alt text](image-2.png)<br><br>Logistic regression scores within 0.013 of itself on every metric between validation and test, so there is no sign of overfitting.|![alt text](image.png)![alt text](image-1.png)![alt text](image-3.png)

## Model Selection
    Logistic Regression is the selected model because of negligible ROC-AUC difference from XGBoost [ROC-AUC: 0.0086] and is simpler and connects to the previous analysis.

## Key Finding
    Logistic regression ranks customers by churn risk better than chance (test ROC AUC 0.72 versus 0.50 for the baseline). At the default 0.5 threshold, however, it labels 91% of customers as churned, so precision (0.795) is only about 3 points above the 76.2% churn rate and F1 (0.866) matches the baseline's (0.865). The model is useful for ordering customers by risk, not for separating churners from non-churners at 0.5.

## Limitations
- **Weak signal:** several analyses showed small effects and very high churn in every segment, which limits what any model can learn.
- **Snapshot data:** one row per customer with no time dimension, so the model cannot predict when a customer will churn.
- **Possible leakage:** inactivity and support calls may be partly a result of churn. This has not yet been tested by refitting without inactivity.
- **Unknown data source:** churn rates are unusually high, so the results may not generalize.
- **Default threshold:** predictions use a 0.5 cutoff, which flags over 90% of customers.

## Environment
- Python, Jupyter Notebook, VS Code, managed with [uv](https://docs.astral.sh/uv/)
- Libraries: pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn
- Exact versions [`pyproject.toml`](../pyproject.toml)