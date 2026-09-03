# Demand Forecasting using Time Series Analysis

A time series forecasting project to analyze weekly product demand and compare different forecasting models for predicting future units sold.

## 📌 Overview

This project analyzes historical sales data and applies time series analysis and forecasting techniques to understand demand patterns and predict future sales.

The project focuses on weekly `units_sold` and explores:

- Data cleaning
- Exploratory Data Analysis (EDA)
- Time series visualization
- Trend and seasonality analysis
- Time series decomposition
- Moving averages
- Autocorrelation
- Holt-Winters Exponential Smoothing
- ARIMA
- Facebook Prophet
- Model comparison using RMSE

## 🎯 Objective

The main objective is to analyze historical demand patterns and determine which forecasting model performs best on the given dataset.

The forecasting models used are:

1. Holt-Winters Exponential Smoothing
2. ARIMA
3. Prophet

The models are evaluated using **Root Mean Squared Error (RMSE)**.

---

## 📊 Dataset

The dataset contains weekly sales information for multiple stores and products (SKUs).

### Important columns

| Column | Description |
|---|---|
| `record_ID` | Unique record identifier |
| `week` | Date of the sales record |
| `store_id` | Store identifier |
| `sku_id` | Product/SKU identifier |
| `total_price` | Selling price |
| `base_price` | Base price of the product |
| `is_featured_sku` | Whether the SKU was featured |
| `is_display_sku` | Whether the SKU was displayed |
| `units_sold` | Number of units sold |

The `week` column is converted to datetime format and the sales data is aggregated into weekly total demand.

---

## 🔧 Project Workflow

```text
Raw Dataset
     ↓
Data Inspection
     ↓
Missing Value Treatment
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Time Series Aggregation
     ↓
Trend & Seasonality Analysis
     ↓
Time Series Decomposition
     ↓
Moving Average Analysis
     ↓
Autocorrelation Analysis
     ↓
Train / Test Split
     ↓
Forecasting Models
 ┌───────────────┬───────────────┬───────────────┐
 ↓               ↓               ↓
Holt-Winters    ARIMA          Prophet
 └───────────────┴───────────────┴───────────────┘
                     ↓
               RMSE Comparison
                     ↓
              Best Model: ARIMA

🧹 Data Cleaning

The dataset was checked for missing values.

A missing value was found in the total_price column.

The missing price was handled by calculating the median total_price for the corresponding sku_id and using it to fill the missing value.

The week column was then converted into datetime format.

🔍 Exploratory Data Analysis

The project explores the distribution and relationships between variables using:

Histograms
Boxplots
Correlation matrix
Heatmap
Time series plots

Some observations from the analysis include:

The dataset contains multiple stores and SKUs.
Most SKUs were neither featured nor displayed.
units_sold has a right-skewed distribution.
Some outliers are present in the price variables.
Featured and displayed SKUs show a positive relationship with units sold.
Price and units sold show a slight negative relationship.
📈 Time Series Analysis

The sales data is aggregated by week to create the demand time series.

The analysis investigates:

Trend

The time series does not show a strong long-term increasing or decreasing trend.

Seasonality

The data shows a repeating seasonal pattern, with evidence of yearly seasonality.

Decomposition

The time series is analyzed in terms of:

Trend
Seasonality
Residuals
Moving Average

4-week and 52-week moving averages are calculated to smooth short-term fluctuations and observe longer-term patterns.

Autocorrelation

Autocorrelation analysis is used to investigate repeating patterns and seasonality in the time series.

🤖 Forecasting Models
1. Holt-Winters

An additive seasonal Holt-Winters model is used with a seasonal period of 52 weeks to capture yearly seasonality.

2. ARIMA

An ARIMA model is trained using:

ARIMA(1, 0, 0)

The model is trained on the first 80% of the weekly time series and evaluated on the remaining 20%.

3. Prophet

Facebook Prophet is used with yearly seasonality enabled to model the demand time series.

📊 Model Evaluation

The models are evaluated using Root Mean Squared Error (RMSE).

Lower RMSE indicates better forecasting performance.

Model	RMSE
Holt-Winters	13,387.60
ARIMA	6,235.74
Prophet	7,710.00
🏆 Best Performing Model

Based on the RMSE obtained in this experiment:

ARIMA performed the best.

ARIMA RMSE = 6,235.74

It achieved the lowest RMSE among the three tested models.

📚 Concepts Practiced

This project helped practice the following Time Series Analysis concepts:

Time series data preprocessing
Datetime conversion
Resampling
Aggregation
Trend
Seasonality
Residuals
Time series decomposition
Moving averages
Autocorrelation
Train-test splitting for time series
Holt-Winters Exponential Smoothing
ARIMA
Prophet
Forecasting
RMSE
Model comparison
🛠️ Technologies & Libraries
Python
Pandas
NumPy
Matplotlib
Seaborn
Statsmodels
Scikit-learn
Prophet
Google Colab
