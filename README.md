# Forecasting Electricity Consumption with and without Covariates

## Project Overview

This project focuses on forecasting electricity consumption for a future period using different time series models, both with and without external covariates such as outdoor temperature.

---

## Methodology

1.  **Data Exploration and Preprocessing**: Transforming raw data into structured time series format.
2.  **Model Selection and Evaluation**: Testing multiple forecasting models, including:
    -   Linear Regression
    -   ARIMA (automatic and manual tuning)
    -   Holt-Winters Exponential Smoothing
    -   Recurrent Neural Networks (RNN)
    -   XGBoost (Machine Learning-based approach)
3.  **Performance Comparison**: Evaluating models using RMSE (Root Mean Square Error) on the test dataset.
4.  **Future Forecasting**: Applying the best-performing models to predict electricity consumption for the target date.

---

## Data Description

The dataset consists of electricity consumption records and outdoor temperature readings collected every 15 minutes from January 1, 2010, to February 17, 2010.

-   **Electricity Consumption (kW)**: The primary target variable.
-   **Outdoor Temperature (°C)**: Used as an external covariate to improve forecasting accuracy.
-   **Time Series Frequency**: The data is recorded every 15 minutes, leading to 96 observations per day.

---

## Model Implementation

### 1. Time Series Models without Covariates

-   **Holt-Winters**: Effective for capturing seasonality and trend changes.
-   **ARIMA**: Automatic and manually tuned versions tested for optimal performance.
-   **RNN (nnetar)**: Neural network-based time series forecasting.
-   **XGBoost**: A machine learning model trained using lagged features.

### 2. Time Series Models with Covariates (Temperature & Temperature²)

-   **Linear & Quadratic Regression**: Initial exploration of the relationship between temperature and electricity consumption.
-   **SARIMA with Covariates**: Seasonal ARIMA model integrating temperature data.
-   **RNN with Covariates**: Using external covariates for enhanced neural network-based forecasting.
-   **XGBoost with Covariates**: Machine learning-based forecasting incorporating temperature and quadratic temperature terms.

---

## Key Findings

-   **Best Model**: XGBoost performed the best in terms of RMSE.
-   **Impact of Covariates**: Incorporating outdoor temperature slightly improved the model's accuracy but added computational complexity.
-   **Time Complexity**: ARIMA models required significantly longer training time compared to machine learning approaches.

---

## Results

The final forecasts were stored in an Excel file `predict.xlsx`, containing predictions for February 17, 2010, in two columns: - **Without Temperature as a Covariate** - **With Temperature as a Covariate**

---

## Usage

### Requirements

Ensure you have the following R packages installed:

``` r
install.packages(c("fpp", "forecast", "readxl", "ggplot2", "lubridate", "xgboost", "writexl"))
```

### Running the Notebook

1.  Load the dataset `Elec-train.xlsx`.
2.  Execute all preprocessing and modeling steps.
3.  Evaluate model performance.
4.  Generate final forecasts and save them to `predict.xlsx`.

---
