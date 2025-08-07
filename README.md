# Time Series Project

A structured exploration of two real‐world monthly time series, applying rigorous EDA, trend/seasonality adjustment, structural‐break analysis, and ARIMA modeling of residuals.

---

## Repository Structure

```text
Time-series-project/
├── Industrial_food_production.ipynb     # R notebook for industrial food‐production series
├── Real_estate_construction.ipynb       # R notebook for real‐estate construction series
└── README.md                            # Project overview and instructions


## Notebooks

### 1. Industrial_food_production.ipynb  
**Dataset:** Monthly industrial food-production (units).  
**Phase 1 – Statistical & Graphical Analysis**  
- **Chronogram** (time plot) and interpretation  
- **Correlogram** (ACF/PACF) and interpretation  
- **Structural decomposition** (additive vs. multiplicative)  

**Phase 2 – Trend & Seasonality Adjustment**  
- **Linear regression** for trend (with model summary)  
- **Harmonic regression** (Fourier terms) for deseasonalization  
- Significance checks and variable selection  

**Phase 3 – ARIMA Modeling of Residuals**  
- Extract adjusted‐residual series  
- **Diagnostics:** ACF/PACF plots, Augmented Dickey–Fuller test  
- Fit candidate `ARIMA(p,0,q)` models and compare by AIC/σ²  
- Select and interpret the best model

---

### 2. Real_estate_construction.ipynb  
**Dataset:** Monthly real-estate construction index (log-transformed).  
**Phase 1 – Statistical & Graphical Analysis**  
- **Chronogram** & **AF/C PACF** on log data  

**Phase 2 – Structural‐Break & Regression**  
- **Breakpoint detection** (`strucchange::breakpoints`) → identify regime shifts  
- **Fourier seasonal terms** (sine/cosine) construction  
- Two regression models:  
  - **Model 1:** full seasonal set  
  - **Model 2:** subset of significant terms  
- Compare model summaries and choose parsimonious fit  

**Phase 3 – ARIMA Modeling of Regression Residuals**  
- Extract `ε₂ = modell2$residuals`  
- **Diagnostics:** ACF/PACF, ADF test on `ε₂`  
- Fit various `Arima(ε₂, order=c(p,0,q))`  
- Evaluate by AIC, residual variance, RMSE/MAE, and whiteness

---

## Prerequisites

- **R ≥ 4.0**  
- Install the following packages in R:  
  ```r
  install.packages(c(
    "readxl",      # Excel I/O
    "tseries",     # ADF test
    "forecast",    # ARIMA modeling
    "strucchange", # Breakpoint detection
    "ggplot2"      # Enhanced plotting
  ))

