# Sales Forecasting with Lasso Regression

## Project Overview

This project involves predicting weekly sales for a retail store using a dataset that includes various features such as store information, historical sales, and promotional data. The dataset is enriched with additional features derived from date information, and advanced preprocessing techniques are employed to handle missing values and prepare the data for modeling.

## Dataset

The dataset includes the following files:
- **stores.csv**: Contains information about the stores.
- **train.csv**: Contains historical sales data.
- **features.csv**: Contains additional information about the sales periods, including promotions and economic indicators.

Walmart is a retail chain with branches worldwide, offering a wide range of products through various store formats and online sales channels.

The dataset features include:
- `Store`: Store number.
- `Dept`: Department number.
- `Date`: Date.
- `Weekly_Sales`: Weekly sales amount.
- `IsHoliday`: Flag indicating if the week is a holiday period (True/False).
- `Size`: Store size in square feet.
- `Temperature`: Average weekly temperature (Fahrenheit).
- `Fuel_Price`: Cost of fuel per gallon.
- `MarkDown1` to `MarkDown5`: Different types of markdowns.
- `CPI`: Consumer Price Index / Inflation.
- `Unemployment`: Unemployment rate.
- `Type`: Store type (A, B, C).

These variables are distributed across the `features.csv`, `train.csv`, and `stores.csv` files.

## Project Steps

1. **Data Loading and Merging**:
   - Loaded data from three CSV files and merged them into a single dataframe for training and testing.

2. **Data Preprocessing**:
   - Converted the `Date` column to datetime format.
   - Created new features: `Week-of-month` and `Quarter`.
   - Converted boolean columns to numeric values.
   - Applied one-hot encoding to categorical features (`Store`, `Dept`, `Type`, `Week-of-month`, `Quarter`).
   - Filled missing values in `MarkDown` columns with 0 and used mean imputation for other missing values.
   - Scaled features to a 0-1 range, excluding `Weekly_Sales`.

3. **Model Training**:
   - Split the data into training and testing sets.
   - Trained a Lasso Regression model to predict `Weekly_Sales`.
   - Lasso was chosen to handle feature selection and prevent overfitting by applying L1 regularization.

4. **Model Evaluation**:
   - Evaluated model performance using Root Mean Squared Error (RMSE) and R-squared (R²).
   - Compared the first 10 predictions with the actual values.

## Usage

To run this project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/sales-forecasting.git
   ```
   
2. Navigate to the project directory:
   ```
   cd sales-forecasting
   ```
   
3. Install the required packages:
   ```
   pip install -r requirements.txt
   ```
   
4. Run the script to train the model and make predictions:
   ```
   python walmart_machine_learning.ipynb
   ```
