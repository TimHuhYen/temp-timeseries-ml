## temp-timeseries-ml
Temperature Time Series Prediction (TMIN)
This project predicts next-day minimum temperature (TMIN) using the past 10 years of weather data and multiple machine learning models.  
The goal is to compare a simple baseline against linear and non-linear models on a real time-series dataset.

## Data
- Source: NOAA daily minimum temperature data
- Location: Edison, New Jersey
- Frequency: Daily

## Models
- **Baseline**: Lag-1 persistence model
- **Ridge Regression**: Linear model with regularization(Standard scaled features, Ridge(alpha=1.0)) and engineered time-series features.
- **Random Forest Regressor**: Non-linear ensemble model

## Features
- Lag features (1, 7 days)
- Rolling window statistics (7, 14 days)
- Seasonal encoding using sin/cos of day-of-year
- Standard scaling for linear models

## Evaluation
Models are evaluated using Mean Absolute Error (MAE) on a time-ordered train/test split.

### Key Findings
- The baseline captures strong seasonality but reacts late to sudden changes
- Ridge regression improves stability and reduces error by regularizing correlated lag features
- Random forest performs best during high-volatility periods by modeling non-linear interactions

## Results
Final comparison plots show:
- Actual vs predicted temperatures
- Error behavior over time for each model

## Tools
- Python
- pandas, numpy
- scikit-learn
- matplotlib
