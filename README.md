# CS_F320_Project_Group1_Topic5
Baseline multinomial logistic regression on Solar Industries India Ltd., a highly traded stock. We applied LSTM, XGBoost, and logistic regression across full and volatility-specific regimes (based on INDIAVIX). Backtests used logistic regression probabilities analyzing returns, max drawdown, and more.
Stock Movement Prediction and Backtesting: Solar Industries India Ltd.
This repository focuses on predicting directional movements of Solar Industries India Ltd., a high-volume traded stock in Indian equity markets, using multiple machine learning models and volatility-based regime analysis.

Project Overview
Models Implemented:

Baseline: Multinomial Logistic Regression for three-class classification (Up, Down, Hold).

Advanced: LSTM (Long Short-Term Memory) networks capturing sequential dependencies and XGBoost enhancing gradient boosting on tabular features.

Volatility Regimes:

Segmentation of stock data based on INDIAVIX (India Volatility Index) into three regimes.

Models are trained and evaluated both on the entire dataset and regime-specific subsets, allowing volatility-aware prediction.

Feature Engineering:

Incorporation of lagged returns, technical indicators (RSI, EMA), volume, and other market metrics.

Handling categorical variables such as EMA comparison and directional classes via encoding.

Imbalanced Data Handling:

Use of SMOTE (Synthetic Minority Over-sampling Technique) to balance target classes during logistic regression training.

Backtesting Framework:

Uses predicted class probabilities from the logistic regression model as trading signals.

Calculates financial metrics such as cumulative return, maximum drawdown, hit rate, and Sharpe ratio for performance evaluation.

Evaluation Metrics:

Precision, recall, F1-score for classification.

Financial evaluation on simulated trading outcomes.

Repository Structure
fods_project_models.py: Implements baseline logistic regression and XGBoost models with feature scaling and SMOTE for imbalance.

fods_project_lstm.py: Defines the LSTM architecture using TensorFlow, with sequential training and test prediction loops.

SOLARINDS_HighVol.csv: Processed stock data containing price, volume, technical indicators, and volatility regime flags.

Project proposal PDF outlining methodology, hypotheses, and analysis framework.

Usage
Data Preparation: Import and preprocess stock data, encode categorical features, and split by date for training and testing.

Feature Scaling & Imbalance Treatment: Standardize numeric features and apply SMOTE to balance classes.

Model Training: Train logistic regression, XGBoost, and LSTM models separately on full and regime-based datasets.

Prediction & Backtesting: Generate predictions and class probabilities; simulate trading strategies using these signals.

Evaluation: Review classification metrics and backtest financial performance to assess practical strategy effectiveness.

Contributions and Extensions
This repository provides a foundational approach to stock movement prediction for one Indian stock, emphasizing volatility-aware modeling. Contributions are welcome for:

Extending to multiple stocks or indices.

Incorporating additional data sources (macroeconomic indicators, news sentiment).

Refining model architectures and hyperparameters.

Improving backtesting robustness with transaction costs and realistic trading constraints.
