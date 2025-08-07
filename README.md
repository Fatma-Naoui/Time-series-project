# Time Series Project

This repository demonstrates time-series analysis and modeling on two real-world datasets. It covers exploratory data analysis (EDA), seasonal–trend decomposition, residual diagnostics, structural-break detection, regression, and ARIMA modeling.

---

## Contents

- **Industrial_food_production.ipynb**  
  - **Data**: Monthly industrial food‐production series  
  - **EDA**  
    - Chronogram (time plot)  
    - Correlogram (ACF/PACF)  
  - **Decomposition**  
    - Additive decomposition  
    - Multiplicative decomposition  
  - **Residual Analysis**  
    - First‐difference of residuals  
    - ACF/PACF of residuals  
    - Augmented Dickey‐Fuller (ADF) test  

- **Real_estate_construction.ipynb**  
  - **Data**: Monthly real‐estate construction series  
  - **EDA**  
    - Chronogram & ACF/PACF (on log‐transformed data)  
  - **Structural-break & Regression**  
    - Breakpoint detection (`strucchange`)  
    - Time trend + seasonal regressors (sine/cosine)  
    - Two linear models (`modell`, `modell2`)  
  - **Decomposition**  
    - Additive & multiplicative decomposition  
  - **Residual Analysis & ARIMA**  
    - Residual diagnostics (ACF/PACF, ADF)  
    - Fit ARIMA(p,0,q) models on regression residuals  

---

## Prerequisites

### R environment  
- **R ≥ 4.0**  
- Install packages:
  ```r
  install.packages(c("readxl", "tseries", "forecast", "strucchange", "ggplot2"))
