# Stock	Price	Prediction:	Three-Class	Classification	with	Volatility-Aware	Trading	Strategy

This repository focuses on **predicting directional movements** of **Solar Industries India Ltd.**, a high-volume traded stock in Indian equity markets, using **machine learning models** and **volatility-based regime analysis**.

---

## Project Overview

### Models Implemented

* **Baseline:**
  Multinomial Logistic Regression for **three-class classification** — *Up*, *Down*, *Hold*.

* **Advanced:**

  * **LSTM (Long Short-Term Memory)** networks capturing sequential dependencies in price movements.
  * **XGBoost** leveraging gradient boosting on engineered tabular features.

---

### Volatility Regimes

* Stock data is segmented using **INDIAVIX (India Volatility Index)** into three volatility regimes:
  **Low**, **Medium**, and **High**.
* Models are trained and evaluated both on:

  * The **entire dataset**, and
  * **Regime-specific subsets**, enabling **volatility-aware prediction**.

---

### Feature Engineering

* Incorporation of:

  * Lagged returns
  * Technical indicators (RSI, EMA)
  * Volume and price-based metrics
* Categorical variables (e.g., EMA comparison, Direction) handled via **encoding**.
* All temporal data aligned and windowed for model input consistency.

---

### Imbalanced Data Handling

* **SMOTE (Synthetic Minority Over-sampling Technique)** applied during Logistic Regression training to ensure class balance across *Up*, *Down*, and *Hold* labels.

---

## Backtesting Framework

* Predicted **class probabilities** (from Softmax Regression and XGBoost) are used as **trading signals**.
* Simulated strategy performance evaluated via:

  * **Cumulative Returns**
  * **Maximum Drawdown**
  * **Win Rate**
  * **Sharpe Ratio**

This enables a direct link between **model accuracy** and **financial profitability**.

---

## Evaluation Metrics

| Category           | Metrics                                                 |
| ------------------ | ------------------------------------------------------- |
| **Classification** | Precision, Recall, F1-Score                             |
| **Financial**      | Cumulative Return, Max Drawdown, Sharpe Ratio, Win Rate |

---

## Repository Structure

```
├── fods_project_models.ipynb     # Implements Logistic Regression, LSTM & XGBoost + Backtest Results
├── FODS_project_eda.ipynb        # Exploratory Data Analysis
├── project_proposal.pdf          # Methodology, hypotheses, and analysis framework
└── README.md                     # Project documentation
```

---

## Usage

### 1. **Data Preparation**

* Import and preprocess stock data
* Encode categorical features
* Split by **date range** for train/test (2010–2019 for training, 2020–2025 for testing)

### 2. **Feature Scaling & Imbalance Treatment**

* Standardize numeric features
* Apply **SMOTE** to balance class representation

### 3. **Model Training**

* Train **Logistic Regression**, **XGBoost**, and **LSTM** models
* Conduct experiments on **full dataset** and **volatility-specific regimes**

### 4. **Prediction & Backtesting**

* Generate directional **predictions** and **class probabilities**
* Simulate **trading strategies** using prediction-based signals

### 5. **Evaluation**

* Compute **classification metrics**
* Perform **backtest analysis** to assess trading performance

---

## Contributions and Extensions

This repository offers a **volatility-aware stock prediction framework** using multiple model families.
You can contribute by extending or refining the system.

### Ideas for Extension:

* Defining volatility locally instead of using a market-wide indicator
* Extension to a portfolio of stocks instead of a single stock
* Utilizing softwares such as TradingView to backtest results using feature importances
* Changing threshold values for direction and volatility quantiles as per retail requirements
* Using CHRONOS library for better time-series predictions
* Apply framework to **multiple Indian equities or indices**
* Incorporate **macroeconomic** or **news sentiment** data
* Optimize **hyperparameters** and **model architectures**


---
