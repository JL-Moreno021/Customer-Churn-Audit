# Dataset Cleaning
    This notebook focuses on cleaning and preparing the raw dataset for analysis. It covers standardizing columns, data inspection, handling missing and invalid values, and removing duplicates.

## Goal
    Produce a clean, consistent, and quality dataset for exploratory data analysis and building a machine learning model.

## Data Limitations
* _Age restrictions_
    - The dataset may contain age values outside the intended customer demographic or target population.

* _Missing time-scale information_
    - Some variables lack clear time-scale definitions (e.g., monthly or annual), making direct comparisons difficult.
    
* _Lack of external validation data_
    - No external data sources are available to independently verify the accuracy of the recorded information.

### Limitation Address
* _Age Restrictions_
    - Minimum age set to `18`; age restriction assumption for subscription type products/services.
* Inconsistent Time Scales
    - Convert applicable variables from annual to monthly values, and vice versa, to establish a consistent time scale for analysis.
* Lack of external validation data
    - Retain the original values while acknowledging that the dataset's accuracy cannot be independently verified using external sources.