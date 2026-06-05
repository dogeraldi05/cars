# USA Cars Analysis

Exploratory data analysis and visualization of used car listings in the USA.

## Files

### Data
- **`USA_cars_datasets.csv`** — original dataset with 2,499 car listings and no missing values. Contains: brand, model, year, price, mileage, color, state, and title status.
- **`USA_cars_datasets_reallife.csv`** — a realistic version of the same dataset with intentional missing values in columns such as `price`, `brand`, `year`, and `mileage`.

### Notebooks
- **`data_cleaning_and_eda.ipynb`** — data cleaning and exploratory analysis applied to the dataset with missing values:
  - Identification and handling of null values per column
  - `brand` imputation via model-to-brand mapping
  - Dropping rows missing `model` or `color` (< 1% of the dataset)
  - `mileage` and `year` imputation using the median grouped by brand, model, and price bracket
  - Prediction of 79 missing prices using three ML models: **XGBoost** (R² 0.92), **Random Forest** (R² 0.96), and **Linear Regression** (R² 0.29)

- **`plots.ipynb`** — exploratory visualizations using the clean original dataset:
  - Average price trend by manufacturing year
  - Price × brand scatter plot colored by mileage
  - Mileage vs. price regression for BMW, Nissan, and Jeep
  - Price distribution by vehicle condition (boxplot)

## Key Findings
- Random Forest was the best model for price imputation (MAE ≈ $1,583).
- Higher mileage consistently reduces price across the three brands analyzed.

