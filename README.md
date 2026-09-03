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
