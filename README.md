# Forecasting-Antidiabetic-Drug-Prescriptions

## Project Overview
The objective of this project is to forecast the number of antidiabetic drug prescriptions in Australia from 1991 to 2008. Accurate forecasting of drug prescriptions is essential for optimizing production, ensuring sufficient supply to meet demand while avoiding overproduction. This project utilizes time series analysis techniques to build a predictive model using data recorded by the Australian Health Insurance Commission.

## Dataset
- **Source**: Australian Health Insurance Commission
- **Shape**: 204 rows × 2 columns (Time, Prescription Count)

## Modeling  

### **1️⃣ SARIMA Model**  

#### **Stationarity Check**  
Before modeling, we must ensure the time series is stationary. The Augmented Dickey-Fuller (ADF) test is used to check stationarity. The original time series was non-stationary, so differencing and seasonal differencing were applied.  

#### **Set Differencing Parameters**  
To achieve stationarity, we determine the differencing parameters:  
- **d**: Order of non-seasonal differencing  
- **D**: Order of seasonal differencing  

#### **Define Model Parameters & Function**  
We define a set of values for the SARIMA model parameters:  
- **p**: Autoregressive order  
- **q**: Moving average order  
- **P**: Seasonal autoregressive order  
- **Q**: Seasonal moving average order  

A function was created to train the SARIMA model using different parameter combinations.  

#### **Fit the Model & Selection**  
The SARIMA model was trained using various parameter combinations, and the best model was selected based on the **Akaike Information Criterion (AIC)**. The model with the lowest AIC value was chosen.  

#### **Residual Analysis**  
To ensure model validity, residual analysis was performed:  
- **Q-Q Plot**: Checked if residuals followed a normal distribution.  
- **Ljung-Box Test**: Tested for autocorrelation in residuals.  

---

### **2️⃣ Holt-Winters Exponential Smoothing**  

#### **Model Selection & Parameters**  
Holt-Winters method was also applied as an alternative to SARIMA. It consists of:  
- **Trend (β)**: Adjusts for increasing or decreasing trends over time.  
- **Seasonality (γ)**: Captures seasonal patterns in the data.  

#### **Fit the Model**  
The model was trained with different smoothing parameters, and the best configuration was selected based on error metrics like **MAPE** and **MAE**.  

---

## Evaluation Metrics  
Both models were compared using:  
- **Mean Absolute Percentage Error (MAPE)**  
- **Mean Absolute Error (MAE)**

---

## **Results**  

The performance of both models was evaluated using **Mean Absolute Percentage Error (MAPE)** and **Mean Absolute Error (MAE)**.  

| Model           | MAPE  | MAE   |  
|----------------|------|------|  
| **SARIMA**     | 7.563 | 1.526 |  
| **Holt-Winters** | 7.125 | 1.422 |  

Holt-Winters performed slightly better than SARIMA, achieving a lower MAPE and MAE.  

---
