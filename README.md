# Predictive_Model_For_Exchange
## Overview
This project aims to forecast short-term exchange rate movements using historical financial data and macroeconomic indicators. The solution includes feature engineering, model training, evaluation, an automated ETL pipeline, and SQL queries for analyzing predictions. 
The goal is to provide a reproducible pipeline for predicting exchange rate fluctuations and assessing model performance.




## Dataset
Data was sourced from the following APIs:
- **Economic Indicators** (GDP, CPI(inflation rate), Interest Rates): Fetched from the [FRED API(Api key : )](https://fred.stlouisfed.org/) using series IDs `GDPC1`, `CPIAUCSL`, and `FEDFUNDS`.
- **Exchange Rates**: Historical daily forex data (e.g., EUR/USD) retrieved from [Alpha Vantage Api key : ](https://www.alphavantage.co/) .

**Date Range**: November 11, 2024 – March 24, 2025 (aligned with the problem statement and Historical daily forex data ).

---
