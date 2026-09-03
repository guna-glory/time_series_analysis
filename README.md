# 📈 Time Series Analysis & Forecasting

A collection of practical **Time Series Analysis and Forecasting projects** implemented using Python.

This repository contains three projects covering different real-world time-series applications:

- 🛒 Retail Demand Forecasting
- 📊 Tesla Stock Price Forecasting
- ⚡ Energy Demand Forecasting

The projects explore time-series patterns such as **trend, seasonality, stationarity, autocorrelation, volatility, and forecasting** using statistical and modern forecasting models.

---

## 📌 Projects

| # | Project | Domain | Forecasting Models |
|---|---|---|---|
| 1 | 🛒 Demand Forecasting | Retail / Sales | Holt-Winters, ARIMA, Prophet |
| 2 | 📊 Tesla Stock Forecasting | Stock Market | Prophet |
| 3 | ⚡ Energy Demand Forecasting | Energy | ARIMA |

---

# 🛒 1. Demand Forecasting

## 📖 Overview

The Demand Forecasting project analyzes historical retail sales data and predicts future product demand using time-series forecasting techniques.

The dataset contains information about stores, products, prices, promotional features, and units sold.

The project first performs exploratory data analysis and then converts the sales data into a weekly time series for forecasting.

### 🎯 Objectives

- Analyze historical product demand.
- Understand the relationship between price and demand.
- Study promotional effects on sales.
- Identify trends and seasonal patterns.
- Analyze demand volatility.
- Apply multiple forecasting models.
- Compare forecasting performance using RMSE.
- Identify the best-performing model.

---

## 📊 Dataset

The dataset contains information such as:

| Feature | Description |
|---|---|
| `record_ID` | Unique record identifier |
| `week` | Week of observation |
| `store_id` | Store identifier |
| `sku_id` | Product/SKU identifier |
| `is_featured_sku` | Whether the product was featured |
| `is_display_sku` | Whether the product was displayed |
| `units_sold` | Number of units sold |
| `total_price` | Total selling price |
| `base_price` | Base price |

---

## 🔧 Data Preprocessing

The project performs several preprocessing steps:

- Dataset inspection
- Missing-value detection
- Date conversion
- Missing-value treatment
- Data aggregation
- Time-series preparation

A missing value in `total_price` is handled using the median `total_price` corresponding to the respective SKU.

The sales data is then aggregated on a **weekly basis**.

---

## 🔍 Exploratory Data Analysis

The analysis investigates:

- Distribution of units sold
- Price distributions
- Base price
- Featured products
- Displayed products
- Relationship between price and demand
- Weekly sales patterns
- Demand volatility

The `units_sold` distribution is right-skewed, while price-related variables contain some outliers.

Featured and displayed SKUs show a positive relationship with units sold, while price has a slight negative relationship with demand.

---

## 📈 Time-Series Analysis

The weekly demand series is analyzed using:

- Moving averages
- Seasonal decomposition
- Weekly percentage changes
- Volatility analysis

The project uses:

- **4-week moving average**
- **52-week moving average**

Seasonal decomposition indicates an annual seasonal component in the demand data.

The standard deviation of the week-to-week percentage change in units sold is approximately **26%**, indicating considerable short-term demand variation.

---

## 🤖 Forecasting Models

Three forecasting approaches are implemented and compared.

### 1. Holt-Winters

An additive Holt-Winters model is used with an annual seasonal period:

```python
seasonal_periods = 52# time_series_analysis

2. ARIMA

An ARIMA model is trained on the weekly demand series.

3. Prophet

Prophet is used with yearly seasonality to forecast future demand.

📊 Model Performance

The models are evaluated using Root Mean Squared Error (RMSE).

Model	RMSE
Holt-Winters	13387.6030
ARIMA	6235.7362
Prophet	7709.9961
🏆 Best Model

Based on the RMSE values recorded in the notebook:

ARIMA achieved the lowest RMSE and performed best among the tested models.

Note: The Holt-Winters implementation produced an optimization/convergence warning in the notebook.

📊 2. Tesla Stock Price Forecasting
📖 Overview

The Tesla Stock Price Forecasting project performs time-series analysis on historical Tesla stock-market data.

The project explores historical stock prices, trading volume, trends, and seasonal behavior before applying Facebook Prophet for forecasting.

🎯 Objectives
Load and inspect historical Tesla stock data.
Analyze stock-price behavior.
Visualize historical closing prices.
Analyze trading volume.
Study trends and seasonal patterns.
Decompose the time series.
Prepare data for Prophet.
Generate future forecasts.
Visualize predicted and historical values.
📊 Dataset

The Tesla stock dataset contains standard stock-market attributes including:

Feature	Description
Date	Trading date
Open	Opening price
High	Highest price
Low	Lowest price
Close	Closing price
Volume	Trading volume
Adj Close	Adjusted closing price

The notebook contains 1,692 records and reports no missing values.

🔍 Exploratory Data Analysis

The project analyzes:

Closing-price trends
Trading volume
Statistical properties
Price variation
Historical growth and decline
Time-series behavior

The closing-price series shows substantial variation over the observed period.

Trading volume also changes considerably over time.

📉 Seasonal Decomposition

The notebook performs seasonal decomposition on the closing-price series.

A multiplicative decomposition is used with a period of:

period = 30

The decomposition separates the time series into:

Observed
   │
   ├── Trend
   ├── Seasonal
   └── Residual

This helps analyze the underlying structure of the stock-price series.

🔮 Prophet Forecasting

The closing-price data is converted into Prophet's required format:

ds → Date
y  → Close

The Prophet model is then initialized and used to generate future predictions.

The notebook creates a future dataframe for:

365 days

The forecast includes:

Predicted values
Upper prediction interval
Lower prediction interval
📈 Forecast Visualization

The project visualizes the historical and predicted stock-price values.

It also supports visualization of Prophet forecast components to examine the structure captured by the model.

Note: The notebook contains a Prophet optimization error during one fitting attempt. Therefore, this project should be treated as a forecasting experiment rather than a production-ready stock prediction system.

⚡ 3. Energy Demand Forecasting with ARIMA
📖 Overview

The Energy Demand Forecasting project analyzes historical electricity demand and solar-energy generation data.

The project uses ARIMA to model and forecast the energy-demand time series.

It also demonstrates important statistical time-series techniques including:

Stationarity testing
Augmented Dickey-Fuller testing
ACF
PACF
Train-test splitting
ARIMA modeling
Actual vs predicted visualization
🎯 Objectives
Load energy-demand data.
Inspect the dataset.
Process timestamp information.
Handle missing values.
Visualize energy demand.
Analyze solar generation.
Test stationarity.
Analyze autocorrelation.
Select ARIMA parameters.
Train an ARIMA model.
Generate predictions.
Compare actual and predicted values.
📊 Dataset

The project uses:

energy_demand.csv

The main columns are:

Column	Description
utc_timestamp	Timestamp of observation
IT_load_new	Electricity load/demand
IT_solar_generation	Solar energy generation

The observations are recorded at hourly intervals.

🔧 Data Preprocessing

The project performs:

Dataset loading
Dataset inspection
Timestamp processing
Missing-value detection
Missing-value treatment
Time-series visualization

The dataset contains missing values in IT_load_new.

These missing values are handled using forward filling.

After preprocessing, the data is ready for time-series analysis.

📈 Exploratory Analysis

The project visualizes electricity load and solar generation over time.

The energy-demand series exhibits recurring patterns.

Solar generation also shows a strong daily pattern, with generation occurring mainly during daylight hours.

📐 Stationarity Analysis

Stationarity is an important requirement when working with ARIMA models.

The project uses the Augmented Dickey-Fuller (ADF) test to determine whether the time series is stationary.

IT Load
ADF Statistic : -11.97390
p-value       : 3.841445e-22
Solar Generation
ADF Statistic : -5.741335
p-value       : 6.265438e-07

Since the p-values are below 0.05, the notebook rejects the null hypothesis of non-stationarity.

Therefore, both series are considered stationary according to the ADF test results.

📊 ACF & PACF Analysis

The project uses:

ACF — Autocorrelation Function
PACF — Partial Autocorrelation Function

These plots help identify suitable ARIMA parameters.

For the IT_load_new series, the PACF analysis shows a sharp drop after lag 2.

The selected ARIMA parameters are:

p = 2
d = 0
q = 2

Therefore, the model used is:

ARIMA(2, 0, 2)
🔮 ARIMA Forecasting

The data is divided chronologically into:

80% → Training Data
20% → Testing Data

The ARIMA model is fitted using the training data.

Predictions are then generated for the test period.

The results are visualized using:

Actual Values
      vs
Predicted Values

The notebook indicates that the ARIMA model captures the general pattern of the time-series data.

🧠 Time-Series Concepts Covered

This repository provides practical implementation of the following concepts.

Data Preparation
Data loading
Data inspection
Datetime conversion
Datetime indexing
Missing-value detection
Missing-value handling
Forward filling
Median imputation
Time-series aggregation
Exploratory Analysis
Time-series visualization
Trend analysis
Seasonality
Moving averages
Volatility
Seasonal decomposition
Price-demand relationships
Statistical Analysis
Stationarity
Augmented Dickey-Fuller test
Autocorrelation
Partial autocorrelation
ACF
PACF
Forecasting
ARIMA
Holt-Winters Exponential Smoothing
Prophet
Train-test splitting
Future forecasting
Model Evaluation
RMSE
Actual vs predicted plots
Forecast visualization
Model comparison
🛠️ Technologies & Libraries

The projects are implemented using Python.

Programming Language
Python
Data Analysis
Pandas
NumPy
Visualization
Matplotlib
Plotly
Statistical Time Series
Statsmodels
Forecasting
ARIMA
Holt-Winters
Prophet
Model Evaluation
Scikit-learn