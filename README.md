# 📈 AQI Time Series Forecasting using Deep Learning & Statistical Models

## 📌 Project Overview

This project focuses on **forecasting Air Quality Index (AQI)** using both **deep learning** and **classical statistical time series models**.  
The dataset consists of **daily AQI observations from 2021 to 31st December 2024**, including date-related features (day, month, year).

The objective is to:
- Explore relationships between features and AQI
- Forecast AQI using **LSTM**, **GRU**, **ARIMA**, and **SARIMA**
- Validate predictions using recent months
- Compare model performance using **RMSE**

---

## 🧠 Problem Statement

Given a daily AQI dataset:
1. Read and clean the dataset
2. Perform **Exploratory Data Analysis (EDA)** to understand AQI behavior
3. Build **deep learning time series models** (LSTM & GRU)
4. Apply **statistical forecasting models** (ARIMA & SARIMA)
5. Compare all models to identify the best-performing approach

---

## 🗂️ Dataset Description

- **Frequency:** Daily  
- **Time Period:** 2021 – 31st December 2024  
- **Features:**
  - `Date`
  - `Day`
  - `Month`
  - `Year`
  - `AQI` (Target Variable)

> For univariate statistical modeling, only **Date** and **AQI** are used.

---

## 🔄 Project Workflow

### 1️⃣ Data Loading & Cleaning
- Load dataset using Pandas
- Handle missing values
- Remove duplicates
- Convert date columns to proper `datetime` format
- Sort data chronologically

---

### 2️⃣ Exploratory Data Analysis (EDA)
- Trend analysis of AQI over time
- Monthly and yearly AQI patterns
- Correlation analysis between AQI and date-related features
- Rolling mean and rolling standard deviation
- Outlier detection

---

### 3️⃣ Data Transformation (For Deep Learning Models)
- Feature scaling using **MinMaxScaler**
- Time-series sequence generation using sliding windows
- Train-test split based on time (no random shuffling)
- Reshape data for LSTM and GRU input requirements

---

### 4️⃣ Deep Learning Models

#### 🔹 LSTM (Long Short-Term Memory)
- Captures long-term temporal dependencies
- Handles non-linear time series patterns effectively

#### 🔹 GRU (Gated Recurrent Unit)
- Faster training compared to LSTM
- Similar performance with fewer parameters

#### 🔧 Hyperparameter Tuning Includes:
- Number of layers
- Number of hidden units
- Learning rate
- Batch size
- Number of epochs

---

### 5️⃣ Deep Learning Model Validation
- Use last **few months** of data for validation
- Forecast AQI values
- Compare predicted vs actual AQI
- Calculate RMSE

---

### 6️⃣ Statistical Time Series Analysis (Univariate)

#### 🔍 Stationarity Checks
- Rolling mean and rolling variance
- Augmented Dickey-Fuller (ADF) Test

#### 🔍 Random Walk & White Noise
- Identify whether AQI follows random walk behavior
- Check for white noise characteristics

#### 🔍 Autocorrelation Analysis
- Autocorrelation Function (ACF)
- Partial Autocorrelation Function (PACF)

---

### 7️⃣ Statistical Models

#### 🔹 ARIMA
- Model AQI using parameters (p, d, q)
- Parameters selected using:
  - ACF plots
  - PACF plots
  - Experimental tuning

#### 🔹 SARIMA (Seasonal ARIMA)
- Applied if seasonality is detected
- Seasonal parameters (P, D, Q, S) tuned accordingly

---

### 8️⃣ Statistical Model Validation
- Forecast AQI for the last few months
- Compare forecasted and actual values
- Compute RMSE

---

### 9️⃣ Model Comparison

Final comparison table:

| Model   | RMSE |
|--------|------|
| LSTM    | 180.81|
| GRU     | 58.83 |
| ARIMA   | 72.17 |
| SARIMA  | 264.6 |
| SARIMAX | 322.5 |

✔️ Lower RMSE indicates better model performance.

---

## 🛠️ Tech Stack

- **Programming Language:** Python  
- **Libraries Used:**
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
  - statsmodels
  - tensorflow / keras

---
