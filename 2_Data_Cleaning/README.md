# Data Cleaning
Prepares the raw customer churn dataset for analysis and modeling: standardizing column names and text labels, handling invalid and missing values, and removing duplicates.

## Goal
Produce a consistent, documented dataset for exploratory analysis, statistical testing, and modeling.

## Cleaning Rules
| Variable | Issue | Rule | Rationale |
|---|---|---|---|
| `age` | Values below 18 or above 70 | Set to missing | Subscription products assume adult customers; upper cutoff set at [reason] |
| `customer_service_calls` | Negative values | Set to missing | A call count cannot be negative |
| `monthly_spend` | Negative values; values above 311.39 | Set to missing | Spend cannot be negative; cutoff set at [reason] |
| Text columns | Inconsistent case, spaces | Lowercase, strip, replace spaces with `_` | Consistent categories |
| All rows | Duplicate records | Drop after all other fixes | Duplicates can appear after standardizing |

## Data Limitations
- **Unverified accuracy:** no external source is available to validate the records.
- **Unknown source:** the dataset's origin is not documented, and churn rates are unusually high, so it may be synthetic.
- **Assumed time scale:** `monthly_spend` is assumed to be monthly.
- **Missing values:** rows with missing values are dropped per analysis, not here.

## How Limitations Were Handled
- **Invalid values:** set to missing instead of deleted, so rows keep their other information.
- **Plausible values:** kept as recorded.
- **Dropped rows:** missing-value rows are compared with complete rows (see the final section) to check for bias.

## Summary of Changes
|Variable|Changes|
---|---
`age`|9267 records => 8718
`customer service calls`|10300 => 10248
`monthly spend`| 9786 => 9715
`Text columns`|converted to snake_case
`Categorical Data`|`gender`: lower case<br>`region`: 8 => 4 lower case<br>`subscription plan`: 6 => 3 lower case<br>`payment method`: 9786 => 9575
`dupilcate records`|300 records dropped