# 📈 U.S. Federal Funds Rate Forecasting using Machine Learning

This project implements a robust framework for time series forecasting of the **U.S. Federal Funds Rate (FEDFUNDS)**. Instead of relying on a single model, it trains, evaluates, and compares multiple econometric and Machine Learning models to find the optimal prediction tool based on comprehensive macroeconomic data.

## 🎯 Project Goal

To build and rigorously benchmark several predictive models—including both linear and non-linear approaches—to accurately forecast the next month's FEDFUNDS rate. The objective is to identify the most performant model (measured by metrics like MSE, MAE, and R²) and use it to generate actionable, short-term rate predictions.

## 📊 Data & Features

The model is trained on historical macroeconomic data for the United States, with **FEDFUNDS** as the **Target Variable**.

| Variable | Description | Role in Model |
| :--- | :--- | :--- |
| **FEDFUNDS** | Federal Funds Rate | **Target (y)** |
| **GS10** | 10-Year Treasury Constant Maturity Rate | Feature (X) |
| **CPIAUCSL** | Consumer Price Index (Inflation proxy) | Feature (X) |
| **Unemployment rate** | Unemployment Rate (Labor Market proxy) | Feature (X) |
| **POP** | U.S. Total Population | Feature (X) |
| **NA000334Q** | Gross National Product (GNP) or similar indicator | Feature (X) |
| **PCE** | Personal Consumption Expenditures | Feature (X) |

## 🛠️ Methodology and Models

The core of the project involves the following steps:

1.  **Data Preparation:** Load and preprocess the monthly data (`US_DATA.xlsx - Monthly.csv`), handling temporal indices and ensuring all features are numeric.
2.  **Train/Test Split:** Data is split into training and testing sets to simulate real-world performance evaluation.
3.  **Model Benchmarking:** A diverse set of models is trained and evaluated using **Cross-Validation (CV)** to ensure robust performance across different data subsets.

### Models Implemented:

| Category | Model Name | Technique Highlights |
| :--- | :--- | :--- |
| **Linear** | **Linear Regression (OLS)** | Baseline linear model. |
| **Regularized** | **Ridge Regression** | L2 regularization for stability and handling multicollinearity. |
| **Regularized** | **Lasso Regression** | L1 regularization for feature selection (driving less impactful coefficients to zero). |
| **Non-Linear** | **Support Vector Regression (SVR)** | Highly versatile non-linear model, optimized via Grid Search. |
| **Ensemble** | **Random Forest Regressor** | Tree-based ensemble method for capturing complex non-linear interactions. |

## ⚙️ Key Technical Features

* **Hyperparameter Tuning:** Optimal $\alpha$ values for Ridge and Lasso are determined using Cross-Validation (`GridSearchCV`).
* **Performance Metrics:** Models are evaluated using Mean Squared Error (**MSE**), Mean Absolute Error (**MAE**), and R-squared ($\mathbf{R^2}$).
* **Next-Step Forecasting:** The code outputs a concrete forecast for the *next month's* FEDFUNDS rate based on the best-performing linear and non-linear models identified during the benchmark phase.
