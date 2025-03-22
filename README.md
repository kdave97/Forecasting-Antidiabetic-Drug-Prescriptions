# Forecasting-Antidiabetic-Drug-Prescriptions

## Project Overview
The objective of this project is to forecast the number of antidiabetic drug prescriptions in Australia from 1991 to 2008. Accurate forecasting of drug prescriptions is essential for optimizing production, ensuring sufficient supply to meet demand while avoiding overproduction. This project utilizes time series analysis techniques to build a predictive model using data recorded by the Australian Health Insurance Commission.

## Dataset
- **Source**: Australian Health Insurance Commission
- **Shape**: 204 rows × 2 columns (Time, Prescription Count)

## Steps Performed

### 1. Stationarity Check
Before modeling, we must ensure the time series is stationary. The Augmented Dickey-Fuller (ADF) test is used to check stationarity. We found the original time series non-stationary and applied differencing and seasonal differencing.

### 2. Set Differencing Parameters
To achieve stationarity, we determine the differencing parameters:
- **d**: Order of non-seasonal differencing
- **D**: Order of seasonal differencing

### 3. Define Model Parameters & Function
We define a set of values for the SARIMA model parameters:
- **p**: Autoregressive order
- **q**: Moving average order
- **P**: Seasonal autoregressive order
- **Q**: Seasonal moving average order

We write a function to train the SARIMA model using different parameter combinations.

### 4. Fit the Model
The SARIMA model is trained on the dataset using various combinations of the defined parameters.

### 5. Model Selection
To choose the best model, we compare different trained models using the **Akaike Information Criterion (AIC)** and select the one with the lowest AIC value.

### 6. Residual Analysis
After fitting the model, residual analysis is performed to check the model's assumptions:
- **Q-Q Plot**: Ensures residuals are normally distributed.
- **Ljung-Box Test**: Checks for autocorrelation in residuals.


