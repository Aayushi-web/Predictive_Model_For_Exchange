# Predictive_Model_For_Exchange
## Overview
This project aims to forecast short-term exchange rate movements using historical financial data and macroeconomic indicators. The solution includes feature engineering, model training, evaluation, an automated ETL pipeline, for analyzing predictions. 
The goal is to provide a reproducible pipeline for predicting exchange rate fluctuations and assessing model performance.




## Dataset
Data was sourced from the following APIs:
- **Economic Indicators** (GDP, CPI(inflation rate), Interest Rates): Fetched from the [FRED API(Api key : )](https://fred.stlouisfed.org/) using series IDs `GDPC1`, `CPIAUCSL`, and `FEDFUNDS`.
- **Exchange Rates**: Historical daily forex data (e.g., EUR/USD) retrieved from [Alpha Vantage Api key : ](https://www.alphavantage.co/) .

**Date Range**: November 11, 2024 – March 24, 2025 (aligned with the problem statement and Historical daily forex data ).

---
## Task 1 : Feature Engineering:
    Key Features Likely to Influence Exchange Rates
 lagged_close (momentum)
 real_interest_rate (interest-inflation balance)
 7d_ma (trend direction)
 daily_range (volatility)
 1. lagged_close (Momentum)
Description: The closing price of the previous day. It captures the momentum of price movements.
Why it's useful: Helps identify trends, as the current exchange rate often follows the previous day's movement.
2. log_return (Interest-inflation Balance)
Description: The percentage change in the closing price, calculated using the natural log of the price ratio.
Why it's useful: Reflects price changes in a normalized form, indicating the rate of return on currency.
3. 7d_ma (Trend Direction)
Description: The 7-day moving average of the closing price.
Why it's useful: Smooths out short-term fluctuations and helps identify the underlying trend of the exchange rate.
4. daily_range (Volatility)
Description: The difference between the high and low prices of the day.
Why it's useful: Measures the volatility of the exchange rate, with higher values indicating more price fluctuation.
5. norm_range (Volatility)
Description: A normalized version of the daily range, scaled to a certain range (e.g., 0 to 1).
Why it's useful: Provides a relative measure of volatility, making it easier to compare across different time periods or currencies.


---
## Task 2 : Model Building:
The goal of Task 2 is to build predictive models for short-term exchange rate movements using machine learning algorithms. The models aim to predict the next day's closing price (or short-term price movement) based on historical financial and economic data.

In this task, we implemented the following models:

Linear Regression
Random Forest
XGBoost

1. Linear Regression:
Linear Regression was implemented as a baseline model. This simple approach predicts the target based on a linear combination of input features.
2. Random Forest:
Random Forest, an ensemble learning technique, was used to capture complex relationships and interactions between features. It works well with non-linear data and is less prone to overfitting compared to individual decision trees.
3. XGBoost:
XGBoost, a gradient boosting model, was used due to its powerful performance on structured/tabular data. It uses boosting techniques to build strong predictive models by combining weak models sequentially.

## Task 3 : Model Evaluation:

The models were evaluated using the following metrics:

Mean Squared Error (MSE): Measures the average squared difference between predicted and actual values. A lower MSE indicates better performance.
R² (Coefficient of Determination): Indicates how well the model explains the variability in the target variable. A higher R² indicates a better fit.

After training and evaluating the models on the test dataset, we obtained the following results:

## Model Evaluation Results

The models were tested for their ability to predict short-term exchange rate movements, and their performance is evaluated using the following metrics:

Root Mean Squared Error (RMSE)
Mean Absolute Error (MAE)

Evaluation Metrics
1. Root Mean Squared Error (RMSE)
RMSE measures the square root of the average squared differences between predicted and actual values. It is sensitive to large errors and penalizes models with large deviations.

The formula for RMSE is:

𝑅
𝑀
𝑆
𝐸
=
1
𝑛
∑
𝑖
=
1
𝑛
(
𝑦
𝑖
−
𝑦
^
𝑖
)
2
RMSE= 
n
1
​
  
i=1
∑
n
​
 (y 
i
​
 − 
y
^
​
  
i
​
 ) 
2
 
​
 
Where:

𝑦
𝑖
y 
i
​
  = Actual value (true value)
𝑦
^
𝑖
y
^
​
  
i
​
  = Predicted value
𝑛
n = Number of data points

## Hyperparameter Tuning for Random Forest
Hyperparameter tuning was performed on the Random Forest model using GridSearchCV to find the best parameters. The key hyperparameters tuned were:

n_estimators (number of trees)
max_depth (maximum depth of trees)
min_samples_split (minimum number of samples required to split a node)
After hyperparameter tuning, the Random Forest model achieved improved performance, with the following best parameters:

n_estimators: 200
max_depth: 10
min_samples_split: 5

