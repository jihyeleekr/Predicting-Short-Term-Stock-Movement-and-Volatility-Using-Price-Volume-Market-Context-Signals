# Stock Movement & Volatility Prediction  
**Course:** Data Science Tools and Applications

---

## 1. Project Description & Motivation

This project uses common data science tools to analyze historical stock market data and predict short-term stock behavior. The goal is to build a reproducible data pipeline that collects financial data, creates features, trains prediction models, and evaluates their performance using standard metrics.
The project focuses on predicting **next-day stock price direction** and **next-day volatility** using historical **OHLCV (open, high, low, close, volume)** data combined with market context features such as index or sector performance. 

This project is scoped to fit a **two-month timeline**, allowing time for data collection, feature engineering, modeling, evaluation, and visualization. If the full scope becomes too ambitious, the project can fall back to a simplified version using only price and volume features.

---

## 2. Project Timeline (8 Weeks)

- **Week 1:** Define project scope, select stock universe, set prediction targets, and design evaluation metrics  
- **Week 2:** Collect historical market data and store it using structured formats (CSV / SQLite)  
- **Week 3:** Data cleaning and preprocessing (handling missing values, aligning trading dates)  
- **Week 4:** Feature engineering using technical indicators and lag-based features  
- **Week 5:** Train baseline models and evaluate performance  
- **Week 6:** Train advanced models and perform hyperparameter tuning  
- **Week 7:** Visualization of results and exploratory analysis of model behavior  
- **Week 8:** Final evaluation, documentation, and presentation preparation  

---

## 3. Project Goals

### Goal 1: Predict Next-Day Price Direction
Predict whether a stock’s closing price will increase or decrease on the next trading day.

- **Problem Type:** Binary classification  
- **Metrics:** Accuracy, F1-score, ROC-AUC  
- **Baseline:** Always predicting “up” or using previous-day price direction  
- **Success Criterion:** Achieve higher performance than baseline models on the test set  

### Goal 2: Predict Next-Day Volatility
Predict the magnitude of the stock’s next-day price movement.

- **Problem Type:** Regression  
- **Metrics:** Mean Absolute Error (MAE), Root Mean Squared Error (RMSE)  
- **Baseline:** Rolling average volatility  
- **Success Criterion:** Lower error than baseline methods  

---

## 4. Data Collection Plan

### Data Sources
- Historical daily stock price data (OHLCV)
- Market index or sector ETF data (e.g., S&P 500 or sector-level ETFs)
- Optional: market volatility indicators (e.g., VIX proxy)

### Data Collection Method
- Data will be collected using financial data APIs and Python libraries such as:
  - [`yfinance`](https://ranaroussi.github.io/yfinance/)
  - [Alpaca Market Data API](https://docs.alpaca.markets/docs/getting-started)
- Data will be stored locally in CSV files and/or a SQLite database to ensure reproducibility.

### Stock Universe
- A fixed set of 10–30 large-cap U.S. stocks to ensure manageable scope and consistent data availability.

---

## 5. Feature Engineering Plan

- Lagged returns (1-day, 3-day, 5-day)
- Moving averages and momentum indicators
- Rolling volatility measures
- Volume-based features
- Market context features (index or sector returns)

All features will be constructed using only past information to avoid data leakage.

---

## 6. Modeling Plan (Optional)

- **Baseline Models:** Logistic regression, linear regression  
- **Advanced Models:** Random Forest, Gradient Boosting, XGBoost  
- Models will be trained using time-series-aware splits rather than random shuffling.

---

## 7. Evaluation & Test Plan

- Use a **time-based split**:
  - Training set: earliest 70% of data  
  - Validation set: next 15%  
  - Test set: final 15%  
- Compare model performance against baseline approaches  
- Evaluate generalization across different market conditions  

---

## 8. Visualization Plan (Optional)

- Time series plots of predicted vs. actual outcomes  
- Confusion matrices and ROC curves for classification  
- Feature importance visualizations  
- Error distribution plots for regression tasks  

---

## 9. Expected Outcomes

By the end of the project, the expected deliverables include:
- Feature-engineered datasets suitable for modeling  
- Trained and evaluated machine learning models  
- Visualizations and analysis demonstrating model performance  
- A final report summarizing findings and limitations
