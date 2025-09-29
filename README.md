# Daily Steps Prediction Using Time Series Analysis

This project uses my own daily step counts from **September** as a dataset to practice time series forecasting.  
The goal was to explore different models, understand their behavior, and compare performance.  

## Dataset
- Data source: personal daily steps recorded in September.  
- Time frame: 30 days of observations.  
- Variable of interest: number of steps per day.  

## Models Tested
I fitted and compared three classical time series models:

1. **Moving Average (MA)**  
   - Captures short-term noise effects.  
   - Residuals showed leftover skew and heavy tails.  

2. **Autoregressive (AR)**  
   - Uses previous values to predict the current one.  
   - Significant negative autocorrelation detected, but still not optimal.  

3. **Autoregressive Integrated Moving Average (ARIMA)**  
   - Combines AR and MA with differencing to handle trends.  
   - Residuals looked the most like white noise, with stable variance and near-normal distribution.  

## Results
- Both MA and AR captured some structure, but left patterns in the residuals.  
- **ARIMA(1,1,0)** provided the best fit:  
  - Significant AR term.  
  - Residuals passed diagnostic checks (Ljung–Box, JB, variance stability).  
  - Forecasts were more reliable with tighter confidence intervals.  

## Key Takeaways
- ARIMA performed best for this dataset.  
- Classical models are powerful even for small, personal datasets.  
- Residual diagnostics (autocorrelation, skew, kurtosis, JB test) are critical for validating models.  

## Next Steps
- Collect a longer dataset (multiple months) to improve forecasts.  
- Explore seasonal ARIMA (SARIMA) if weekly patterns emerge.  
- Compare with machine learning methods (e.g., LSTM, XGBoost) for fun.  

---
