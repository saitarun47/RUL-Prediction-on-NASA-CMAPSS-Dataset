# RUL-Prediction-on-NASA-CMAPSS-Dataset
# Remaining Useful Life Prediction on NASA Turbofan Engine Dataset

This project builds a machine learning model to estimate the **Remaining Useful Life (RUL)** of aircraft engines using the NASA CMAPSS (FD001) dataset. It aims to enable predictive maintenance by forecasting how many operational cycles an engine has left before failure.

---

## Problem Statement

Given multivariate sensor readings from turbofan engines over time, the goal is to predict the **RUL** at any point in its life cycle. The problem is treated as a supervised regression task.

---

## Features

- Unit-wise splitting to prevent data leakage  
- Feature scaling with `StandardScaler`  
- Model training with **Random Forest** and **LSTM**  
- Hyperparameter tuning using `GridSearchCV`  
- Evaluation on hold-out validation set using MAE, MSE, R²  


---

## Dataset

**Source:** [NASA CMAPSS FD001 Dataset](https://www.nasa.gov/content/prognostics-center-of-excellence-data-set-repository/)

- 100 engines in training set  
- Each unit (engine) has time-series data over operational cycles  
- 21 sensor readings + operational settings per timestep  
- RUL (Remaining Useful Life) computed for each cycle

---

## Models Used

- **Random Forest Regressor**  
  - Grid-searched on number of estimators and tree depth  
- **Bi-LSTM**  
  - Single-hidden-layer model with early stopping

---

## Evaluation Metrics on test data

- 🔹 Mean Absolute Error (MAE)  : 10.5977
- 🔹 Mean Squared Error (MSE)   : 244.5926
- 🔹 R² Score                   : 0.8584


To ensure robust validation, engines are split at the **unit level** to avoid leakage across time series.

---


