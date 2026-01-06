# Time Series Forecasting on Stock Data

This repository contains my work on **time series forecasting of stock prices** using both **classical statistical model (ARIMA)** and **deep learning model (LSTM)**. The project focuses on understanding, implementing, and comparing different forecasting approaches on real-world financial data.

---

## 📌 Project Overview

- **Dataset**: Tesla Inc. (TSLA) daily stock prices  
- **Data Source**: Yahoo Finance (`yfinance` API)
- **Target Variable**: Closing Price
- **Forecasting Horizon**: Test split based forecasting
- **Programming Language**: Python

The project is divided into two main parts:

1. **Week 1** – Time Series Forecasting using ARIMA  
2. **Week 2** – Comparative Study of ARIMA vs LSTM

---

## 📂 Repository Structure

- Week1_ARIMA
  - notebook.ipynb
  - report.pdf
- Week2_ARIMA_vs_LSTM
  - notebook.ipynb
  - report.pdf
- README.md

---

## 🧠 Week 1: ARIMA-Based Forecasting

### Objectives
- Collect real-world stock price data
- Perform stationarity analysis
- Select optimal ARIMA parameters using grid search
- Generate forecasts and evaluate performance

### Key Steps
- **Stationarity Testing**: Augmented Dickey-Fuller (ADF) test  
- **Differencing**: Applied first-order differencing (`d = 1`)
- **Model Selection**: Grid search over `(p, d, q)` using AIC
- **Evaluation Metrics**:
  - MAE
  - MSE
  - RMSE
- **Residual Analysis**: Checked for white-noise behavior

### Key Observation
The ARIMA model produced a **nearly flat (straight-line) forecast**, which is expected for financial time series behaving like a **random walk without drift**. This highlights the limitations of linear models on volatile stock data.

---

## 🤖 Week 2: ARIMA vs LSTM Comparison

### Models Implemented
- **ARIMA** (Statistical, linear model)
- **LSTM (Long Short-Term Memory)** neural network

### LSTM Methodology
- Sliding window sequence generation
- Min-Max normalization
- Train-validation split
- Loss monitoring over epochs

### Comparative Insights

| Aspect | ARIMA | LSTM |
|------|------|------|
| Linear Patterns | Strong | Moderate |
| Non-linear Patterns | Weak | Strong |
| Long-Term Dependencies | Limited | Excellent |
| Forecast Shape | Flat / Mean-based | Closely follows actual data |

### Learning Curves
- Training and validation loss curves showed **stable convergence**
- No significant overfitting observed
- Validation loss closely followed training loss

### Key Conclusion
- **ARIMA** serves as a strong baseline but struggles with highly volatile data
- **LSTM** effectively captures non-linear trends and short-term fluctuations
- Deep learning models are better suited for complex financial time series

---

## 🛠️ Technologies & Libraries

- Python
- NumPy
- Pandas
- Matplotlib
- statsmodels
- scikit-learn
- TensorFlow / Keras
- yfinance
