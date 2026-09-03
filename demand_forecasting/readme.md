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