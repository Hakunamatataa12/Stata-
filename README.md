# Swedish GDP, Forecasting, and AR(1) Process Analysis – Stata Project

This repository contains several econometric analyses using Swedish GDP data, financial forecasts, and AR(1) time series simulations, performed in Stata.

---

## Problem 1: Real Swedish GDP Trend (2000Q1–2025Q1)

### 1.1 OLS Regression of GDP on Time

- **Image 1:**  
  - Shows OLS regression output for Swedish real GDP regressed on a linear time trend (2000Q1–2019Q4).
  - The slope is 4,695.9 per quarter (SE 59.8), intercept is 563,923.5 (SE 3,755.7)—both highly significant (p < 0.001).
  - R² = 0.9831, F-statistic = 6,163, indicating time is highly significant and the model explains nearly all GDP variation.
  - The fitted trend (red line) closely tracks actual GDP (blue line), with dips around 2008 (financial crisis) and 2020 (COVID).
  - Forecasts show GDP reaching 1.1–1.2 million SEK by end of 2022.

### 1.2 GDP Extended to 2025

- GDP rebounds after the COVID dip and by 2025Q1 lies slightly above the long-term linear trend, indicating sustained growth.

### 1.3 Comparison with HP Filter

- HP filter trend (green) follows medium-term ups and downs, smoothing crises more gently than the linear OLS trend.
- HP filter captures non-linear deviations missed by the OLS trend.

### 1.4 Business Cycle Components

- The cyclical component from the HP filter (blue) and OLS residuals (red) both identify peaks and troughs corresponding to expansions and recessions, with HP-based cycles being smoother.

---

## Problem 2: Seasonality and Trend in Quarterly Data

- Simulates quarterly data with seasonal, trend, and noise components.
- Regression on quarterly dummies (with and without intercept) estimates seasonal effects.
- Detrending reveals true seasonal impacts: Q1 = ~1.4, Q2 = ~2.5, Q3 = ~3.0, Q4 = ~2.0.
- OLS recovers the true time trend (slope ~0.1).
- Dummies explain nearly all variation in the detrended series (R² > 0.98).

---

## Problem 3: Moving Average and EWMA Trading Strategies

- Plots Microsoft and S&P 500 prices with MA(10) and EWMA(α=0.2) filters.
- MA(10) smooths noise but reacts slowly to big moves; EWMA adapts more quickly to peaks and troughs.
- Buy-and-hold outperforms MA/EWMA strategies, but both filters still generate small positive returns.

---

## Problem 4: Forecast Comparison (Repo Rate & EUR/SEK)

- Compares Random Walk and Prospera forecasts for the Swedish repo rate and EUR/SEK exchange.
- RMSFE: Prospera is better for repo rate, Random Walk for EUR/SEK.
- Diebold–Mariano test: OLS shows significant differences, but after Newey–West HAC correction, differences are not statistically significant.
- Strong autocorrelation in forecast errors—Durbin–Watson and correlograms confirm.

---

## Problem 5: AR(1) Process – Theory vs. Simulation

- Compares theoretical unconditional mean and standard deviation with Monte Carlo simulations for AR(1) processes under different parameter sets.
- Simulated means and standard deviations closely match theory.
- Conditional mean and volatility plots for φ = 0.9 and φ = 0.99 show rapid vs. slow convergence.
- When φ is close to 1, initial value effects persist much longer.

---

## Files

- `gdp_trend_analysis.do`: Stata code for GDP trend, HP filter, and cyclical analysis
- `forecasting_analysis.do`: Stata code for forecast comparison, error diagnostics, DM test
- `ar1_simulation.do`: Stata code for AR(1) process simulation and theoretical checks
- `sweden_gdp_data.xlsx`: GDP time series data
- `repo_eur_forecast_data.xlsx`: Forecast and actual data for repo rate and EUR/SEK
- `images/`: Folder for regression outputs and plots (see [Image 1](images/Image1.png) for GDP regression/trend)
- `README.md`: Project summary and interpretation

---
