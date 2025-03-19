# Time Series Forecasting with Holt-Winters, ARIMA, and SARIMA

This project focuses on time series forecasting using various statistical and machine learning models, including **Smoothing Methods (Holt-Winters)**, **ARIMA**, and **SARIMA**. The dataset used is the **Atmospheric CO2 from Continuous Air Samples at Mauna Loa Observatory, Hawaii, U.S.A.**, covering the period from March 1958 to December 2001.

## Table of Contents
- [Dataset](#dataset)
- [Time Series Analysis](#time-series-analysis)
- [Forecasting Methods](#forecasting-methods)
  - [Smoothing Methods (Holt-Winters)](#smoothing-methods-holt-winters)
  - [ARIMA](#arima)
  - [SARIMA](#sarima)
- [Hyperparameter Optimization](#hyperparameter-optimization)
- [Results](#results)

---

## Dataset

The dataset consists of monthly measurements of atmospheric CO2 levels recorded at the Mauna Loa Observatory. It is preprocessed by:
- Resampling the data to a monthly frequency (`MS`).
- Handling missing values using backward fill (`bfill`).
- Splitting the dataset into **training (1958-1997)** and **testing (1998-2001)**.

---

## Time Series Analysis

### Structural Analysis
- **Dickey-Fuller Test:** Used to check stationarity.
- **Decomposition:** Breaking down the series into **trend, seasonality, and residuals**.

### Visualization
- Original CO2 levels are plotted to observe trends and seasonal effects.

---

## Forecasting Methods

### Smoothing Methods (Holt-Winters)

Smoothing methods provide a simple and effective way to model time series data:

1. **Single Exponential Smoothing (SES):** Captures only the level of the series.
2. **Double Exponential Smoothing (DES):** Models **trend** in addition to the level.
3. **Triple Exponential Smoothing (TES or Holt-Winters):** Captures **level, trend, and seasonality**.

Hyperparameter tuning is performed for each model to find the optimal smoothing parameters.

---

### ARIMA (AutoRegressive Integrated Moving Average)

ARIMA is a widely used statistical method for time series forecasting:

- **AR (AutoRegressive):** Uses past values to predict the future.
- **I (Integrated):** Differencing is used to make the series stationary.
- **MA (Moving Average):** Uses past forecast errors to improve predictions.

The best ARIMA model is selected based on **AIC (Akaike Information Criterion)**.

---

### SARIMA (Seasonal ARIMA)

SARIMA extends ARIMA by incorporating seasonality:

- **Seasonal terms** are added to capture repeating patterns in the data.
- The best SARIMA model is selected based on **AIC and MAE (Mean Absolute Error).**

---

## Hyperparameter Optimization

Each model undergoes hyperparameter tuning:

- **SES/DES/TES:** Optimal smoothing parameters (`alpha`, `beta`, `gamma`) are selected.
- **ARIMA/SARIMA:** Best parameters (`p, d, q, P, D, Q, m`) are found by evaluating different model combinations.

---

## Results

- **Smoothing Models:** Holt-Winters TES provided better results for capturing seasonality.
- **ARIMA:** Showed strong performance but struggled with seasonal components.
- **SARIMA:** Performed the best by effectively modeling both trend and seasonality.

The **best model** can be chosen based on **forecast accuracy (MAE, AIC).**

