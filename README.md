# Comparative Analysis of Time Series Forecasting Approaches: Statistical and ML Models

A comprehensive research project comparing **Statistical** and **Machine Learning** models for time series forecasting, applied to the **Bank Nifty (NSE) stock index**.

---

## 📌 Project Overview

This project was developed as part of the **Data Science curriculum at IIT Madras** by **Sohit Pathak (MA22M019)**. It evaluates and compares the forecasting performance of four models on the Bank Nifty (NSEBANK) daily stock index.

The goal is to identify which approach — traditional statistical models or modern ML-based models — provides more accurate predictions for financial time series data.

---

## 📁 Repository Structure

```
├── ARIMA -for-Bank Nifty.ipynb              # Standard ARIMA model
├── Rolling ARIMA -for-Bank Nifty.ipynb      # Rolling Window ARIMA model
├── SVR-Bank_Nifty-prediction.ipynb          # Support Vector Regression model
├── xgboost-Bank_Nifty-prediction.ipynb      # XGBoost Regression model
└── Sohit_Pathak_MA22M019.pdf                # Full Research Report
```

---

## 📊 Dataset

- **Source:** NSE Bank Nifty Index (`^NSEBANK.csv`)
- **Period:** September 2022 – September 2023
- **Rows:** 250 trading days
- **Features:** `Open`, `High`, `Low`, `Close`, `Adj Close`, `Volume`
- **Target Variable:** `Adj Close` (Adjusted Closing Price)
- **Train/Test Split:** 80% Training / 20% Testing

---

## 🔬 Models Compared

### 1. 📈 ARIMA (Autoregressive Integrated Moving Average)
- **Type:** Statistical
- **Notebook:** `ARIMA -for-Bank Nifty.ipynb`
- A standard ARIMA model fitted on the entire training set.
- ACF and PACF plots used to determine AR order.
- Model: `ARIMA(1, 0, 0)` — AR process with lag 1.
- Evaluated on the test set using MSE and MAPE.

### 2. 🔄 Rolling ARIMA
- **Type:** Statistical
- **Notebook:** `Rolling ARIMA -for-Bank Nifty.ipynb`
- A **walk-forward (rolling) validation** approach where the model is refitted at each step using all available historical data.
- Model: `ARIMA(7, 0, 0)` — AR process with lag 7.
- **Results:**
  - ✅ MAPE: **0.51%**
  - ✅ MSE: **81,853.846**

### 3. 🤖 SVR (Support Vector Regression)
- **Type:** Machine Learning
- **Notebook:** `SVR-Bank_Nifty-prediction.ipynb`
- Applies a kernel-based regression model (SVM family) to predict stock prices.
- Dataset: 152 rows × 7 features.

### 4. ⚡ XGBoost (Extreme Gradient Boosting)
- **Type:** Machine Learning
- **Notebook:** `xgboost-Bank_Nifty-prediction.ipynb`
- Uses the `XGBRegressor` with hyperparameter tuning.
- **Key Parameters:**
  - `max_depth=10`
  - `n_estimators=200`
  - `learning_rate=0.05`
  - `gamma=0.001`
  - `random_state=40`

---

## ⚙️ Tech Stack

| Library         | Purpose                              |
|----------------|--------------------------------------|
| `pandas`        | Data loading and preprocessing       |
| `numpy`         | Numerical operations                 |
| `matplotlib`    | Data visualization                   |
| `statsmodels`   | ARIMA modeling                       |
| `scikit-learn`  | SVR, metrics (MSE, MAPE)             |
| `xgboost`       | XGBoost Regression                   |

---

## 📏 Evaluation Metrics

- **MAPE** – Mean Absolute Percentage Error
- **MSE** – Mean Squared Error (also RMSE used in some notebooks)

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib statsmodels scikit-learn xgboost
```

### Running the Notebooks

1. Clone the repository:
   ```bash
   git clone https://github.com/sohit-pathak/Comparative-Analysis-of-Time-Series-Forecasting-Approaches-Statistical-and-ML-Models.git
   cd Comparative-Analysis-of-Time-Series-Forecasting-Approaches-Statistical-and-ML-Models
   ```

2. Download the Bank Nifty dataset (`^NSEBANK.csv`) and place it in the expected path or update the file path in notebooks.

3. Open any notebook with Jupyter:
   ```bash
   jupyter notebook
   ```

---

## 📄 Research Report

The full research report is available in `Sohit_Pathak_MA22M019.pdf`, which includes detailed methodology, results, analysis, and conclusions.

---

## 👤 Author

**Sohit Pathak**  
Roll No: MA22M019  
IIT Madras

---

## 📝 License

This project is for academic and research purposes.
