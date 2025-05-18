# 📈 Forecasting Apple Stock Price using Four Time Series Models

**Author:** Akhila Atmakuru 

**Project Type:** Comparative Modelling / Time Series Forecasting

**Tech Stack:** Python, ARIMA, LSTM (Keras), Transformer (PyTorch), Prophet, yFinance, Matplotlib, Scikit-learn

---

## 🧠 Project Overview

This project explores and compares four different algorithms for forecasting Apple Inc. (`AAPL`) stock prices, using historical data from 2015 to 2024. The aim is to examine how traditional statistical methods perform compared to modern deep learning and hybrid approaches when applied to real-world financial time series data.

---

## 📊 Data

* **Source:** [Yahoo Finance](https://finance.yahoo.com/)
* **Ticker:** AAPL
* **Period:** 2015-01-01 to 2024-12-31
* **Frequency:** Daily closing prices
* **Preprocessing:** Missing values dropped, and for LSTM/Transformer models, data was scaled using `MinMaxScaler`.

---

## 🔍 Models Compared

| Model           | Type                    | RMSE  | MSE    | MAE   |
| --------------- | ----------------------- | ----- | ------ | ----- |
| **ARIMA**       | Statistical (ARIMA)     | 24.21 | 585.94 | 21.85 |
| **LSTM**        | Deep Learning (Keras)   | 5.48  | 30.01  | 4.63  |
| **Transformer** | Deep Learning (PyTorch) | 22.81 | 520.52 | 18.49 |
| **Prophet**     | Additive Time Series    | 18.33 | 335.81 | 16.66 |

---

## 🧪 Observations & Analysis

### 1. **LSTM (Winner)** 🏆

* **Best performance** in all metrics (lowest RMSE, MSE, and MAE).
* Its strength lies in its ability to capture **long-term dependencies** and **nonlinear patterns**, especially useful for financial data.
* Requires proper sequence construction and scaling, but results were significantly better than other models.

### 2. **Prophet**

* Easy to implement and very interpretable.
* Handles seasonality and trend shifts quite well.
* While not as accurate as LSTM, it performed better than ARIMA and Transformer with much less tuning.
* Suitable when domain experts need **explainable forecasts**.

### 3. **Transformer**

* Surprisingly underperformed compared to LSTM.
* Likely due to relatively short sequence length and limited complexity in daily stock trends.
* Transformers shine with **larger datasets** or **multivariate sequences**, which wasn’t the case here.

### 4. **ARIMA**

* Traditional and statistically grounded, but assumes linearity and stationarity.
* Not well-suited to complex, noisy, and nonlinear data like stock prices.
* Poor performance reflects these limitations.

---

## 💡 Conclusion

> **LSTM clearly outperforms all other models** in this setting, demonstrating the strength of deep learning for time series forecasting when data is properly structured and sequences are long enough to capture trends.

However, each model brings value depending on the context:

* Use **ARIMA** for fast baselines and statistical testing.
* Use **Prophet** when interpretability and seasonality detection are crucial.
* Use **LSTM** when accuracy is the top priority.
* Explore **Transformers** in more complex settings or when using multivariate time series data.

---

## 📁 Repository Structure

```
.
├── Forecasting_Apple_Stock_Price.ipynb
├── README.md
└── requirements.txt
```
