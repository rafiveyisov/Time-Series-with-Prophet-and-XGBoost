# ⚡ Hybrid Time Series Forecasting (Prophet + XGBoost)

## 📌 Project Overview

This project implements a **hybrid forecasting system** for hourly electricity demand across multiple US regions.

The approach combines:

- 📈 **Prophet** → captures trend and seasonality
- 🤖 **XGBoost** → models residual errors using engineered features
- 🔁 **Hybrid Model** → final prediction = Prophet + XGBoost residual correction

---

## 🎯 Objective

Improve forecasting accuracy by:
- Modeling long-term structure (Prophet)
- Learning nonlinear residual patterns (XGBoost)
- Combining both into a hybrid system

---

## 🧠 Methodology

### 1. Prophet Baseline
- Daily, weekly, and yearly seasonality
- Trend decomposition
- Produces baseline forecast (`yhat`)

### 2. Residual Modeling
Residuals are calculated as:
residual = actual - prophet_prediction

### 3. XGBoost Enhancer
XGBoost is trained on:
- Lag features
- Rolling statistics
- Time-based features (hour, day, month)

### 4. Hybrid Forecast
final_prediction = prophet_prediction + xgboost_residual_prediction


---

## 📊 Results Summary

The hybrid model significantly improves performance across all datasets.

### 🔹 AEP_hourly
- Prophet MAE: 1305.26 | MAPE: 0.0852  
- Hybrid MAE: **688.64** | MAPE: **0.0456**  
- Best iteration: 206  

### 🔹 COMED_hourly
- Prophet MAE: 1030.17 | MAPE: 0.0902  
- Hybrid MAE: **416.24** | MAPE: **0.0371**  
- Best iteration: 305  

### 🔹 DAYTON_hourly
- Prophet MAE: 188.48 | MAPE: 0.0921  
- Hybrid MAE: **66.98** | MAPE: **0.0331**  
- Best iteration: 326  

### 🔹 DEOK_hourly
- Prophet MAE: 317.32 | MAPE: 0.1033  
- Hybrid MAE: **108.94** | MAPE: **0.0373**  
- Best iteration: 711  

### 🔹 DOM_hourly
- Prophet MAE: 1324.55 | MAPE: 0.1143  
- Hybrid MAE: **418.04** | MAPE: **0.0382**  
- Best iteration: 262  

### 🔹 DUQ_hourly
- Prophet MAE: 136.13 | MAPE: 0.0842  
- Hybrid MAE: **74.23** | MAPE: **0.0463**  
- Best iteration: 520  

### 🔹 EKPC_hourly
- Prophet MAE: 227.77 | MAPE: 0.1492  
- Hybrid MAE: **85.83** | MAPE: **0.0585**  
- Best iteration: 509  

### 🔹 FE_hourly
- Prophet MAE: 620.04 | MAPE: 0.0795  
- Hybrid MAE: **232.97** | MAPE: **0.0305**  
- Best iteration: 254  

### 🔹 NI_hourly
- Prophet MAE: 883.51 | MAPE: 0.0740  
- Hybrid MAE: **370.89** | MAPE: **0.0320**  
- Best iteration: 483  

### 🔹 PJME_hourly
- Prophet MAE: 3097.23 | MAPE: 0.0961  
- Hybrid MAE: **1158.26** | MAPE: **0.0369**  
- Best iteration: 148  

### 🔹 PJMW_hourly
- Prophet MAE: 527.99 | MAPE: 0.0909  
- Hybrid MAE: **161.52** | MAPE: **0.0286**  
- Best iteration: 220  

### 🔹 PJM_Load_hourly
- Prophet MAE: 2332.44 | MAPE: 0.0747  
- Hybrid MAE: **1170.16** | MAPE: **0.0391**  
- Best iteration: 279  

---

## 📈 Key Insights

- Hybrid model consistently reduces error across all datasets
- Average improvement: **~50–65% MAE reduction**
- Residuals contain strong predictive signal
- XGBoost effectively captures nonlinear patterns missed by Prophet

---

## ⚙️ Tech Stack

- Python
- Prophet
- XGBoost
- Pandas
- NumPy
- Scikit-learn
- Optuna (AutoML tuning)

---

## 🚀 Conclusion

This project demonstrates that combining:
> **statistical forecasting (Prophet)** + **machine learning (XGBoost)**

leads to significantly improved forecasting performance for energy demand prediction.

---

## 👨‍💻 Author

AI / ML Engineering Project
