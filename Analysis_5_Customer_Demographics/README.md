# Customer Demographics and Churn
    Are region, payment method, age, or gender associated with customer churn?

## Deliverables
- [Analysis notebook](customer_demographics_and_spending.ipynb): chi-squared tests, age logistic regression, region likelihood-ratio test, regional churn rates, effect size
- [Executive summary](executive_summary.md): findings and recommendation for a non-technical reader

## Testing Approach
- **Chi-squared tests of independence** for region, gender, and payment method.
- **Logistic regression** for age.
- **Likelihood-ratio test** to check whether region still matters after accounting for monthly spend, support calls, inactivity, and age.
- **Cramér's V** to measure how strong the region association is.

## Key Finding
Only region is associated with churn (71.5% in the East to 79.1% in the South), and the effect is very weak (Cramér's V = 0.066).

## Project Limitations
- **Data:** single snapshot with no time information; unknown source and unusually high churn; about a quarter of customers excluded for missing values.
- **Analysis:** shows association, not cause; limited set of variables; no external validation.

## Environment
- Python with Jupyter Notebook in Visual Studio Code, managed with [uv](https://docs.astral.sh/uv/)
- Libraries: pandas, numpy, scipy, statsmodels, matplotlib, seaborn
- Exact versions are pinned in [`pyproject.toml`](../pyproject.toml)