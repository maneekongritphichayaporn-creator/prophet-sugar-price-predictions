# Data Description

`data_collection.csv` is a daily time-series dataset. Each row represents one day.

| Column(s) | Description |
| --- | --- |
| `ID` | Sequential identifier for the row/day. |
| `column_1` to `column_40` | Numeric input features that may represent commodity prices, exchange rates, or other economic indicators. |
| `sugar_price` | Numeric sugar price for that day; this is the target value. |

The CSV header contains 42 columns in this order: `ID`, `column_1` through `column_40`, and `sugar_price`. Use numeric values for the features and target, and keep the header names unchanged. The actual feature meanings and company data are private and are not provided here.

## Forecast output

The notebook writes `submission.csv` with 365 rows and this header:

| Column | Description |
| --- | --- |
| `ID` | Forecast day number, from 1 to 365. |
| `Prediction` | Predicted sugar price for that day. |

[`sandbox_submission.csv`](sandbox_submission.csv) illustrates this output format; its values are not a forecast to rely on.