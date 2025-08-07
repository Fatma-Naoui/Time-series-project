# Time Series Project

A structured exploration of two real-world monthly time series, applying EDA, trend/seasonality adjustment, structural-break analysis and ARIMA modeling of residuals.

---

## Repository Structure

    Time-series-project/
    ├── Industrial_food_production.ipynb   R notebook for industrial food-production series
    ├── Real_estate_construction.ipynb     R notebook for real-estate construction series
    └── README.md                          Project overview and instructions

---

## Notebooks

### Industrial_food_production.ipynb  
**Dataset:** Monthly industrial food-production (units)

**Phase 1 – Statistical & Graphical Analysis**  
- Chronogram (time plot)  
- Correlogram (ACF/PACF)  

**Phase 2 – Trend & Seasonality Adjustment**  
- Linear regression for trend  
- Harmonic regression (Fourier terms) for deseasonalization  
- Significance checks and variable selection  

**Phase 3 – ARIMA Modeling of Residuals**  
- Extract adjusted-residual series  
- Diagnostics: ACF/PACF plots, Augmented Dickey-Fuller test  
- Fit candidate ARIMA(p,0,q) models and compare by AIC and residual variance  
- Select and interpret the best model  

---

### Real_estate_construction.ipynb  
**Dataset:** Monthly real-estate construction index (log-transformed)

**Phase 1 – Statistical & Graphical Analysis**  
- Chronogram (time plot)  
- Correlogram (ACF/PACF)  

**Phase 2 – Structural-Break & Regression**  
- Breakpoint detection via `strucchange::breakpoints()`  
- Fourier seasonal terms (sine/cosine) generation  
- Fit two regression models:  
  1. Full set of Fourier terms  
  2. Subset of significant terms  
- Compare summaries and choose parsimonious fit  

**Phase 3 – ARIMA Modeling of Regression Residuals**  
- Extract residuals from Model 2  
- Diagnostics: ACF/PACF, ADF test on residuals  
- Fit various ARIMA(p,0,q) models on residuals  
- Evaluate by AIC, residual variance, RMSE/MAE and whiteness  

---

## Prerequisites

- **R ≥ 4.0**  
    ```r
    install.packages(c(
      "readxl",      # Excel I/O
      "tseries",     # ADF test
      "forecast",    # ARIMA modeling
      "strucchange", # Breakpoint detection
      "ggplot2"      # Enhanced plotting
    ))
    ```
- **Jupyter** (optional, for running `.ipynb` files)

---

## Usage

1. **Clone the repository**  
   ```bash
   git clone https://github.com/Fatma-Naoui/Time-series-project.git
   cd Time-series-project
