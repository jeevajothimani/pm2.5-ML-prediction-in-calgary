# PM2.5 Air Quality Prediction — Calgary

Machine learning models for hourly PM2.5 forecasting using
meteorological data from a Calgary monitoring station.
Built as a course project for ENCH 675 (Data Science & ML
in Chemical Engineering) at the University of Calgary.

## Results summary

| Model | R² | RMSE (µg/m³) | MAE (µg/m³) |
|---|---|---|---|
| Basic Linear Regression | 0.026 | 6.99 | 5.31 |
| Full Linear (engineered) | 0.964 | 1.33 | 0.82 |
| Ridge / Lasso | 0.964 | 1.33 | 0.82 |
| KNN Regressor | 0.783 | 3.30 | 2.40 |
| **Random Forest** | **0.978** | **1.09** | **0.65** |

**Best model:** Random Forest with engineered lag/rolling features
(R²=0.978, RMSE=1.09 µg/m³).

## Dataset

- ~17,400 hourly observations from a Calgary air quality station
- Features: temperature, dew point, humidity, wind speed/direction
- Target: PM2.5 concentration (µg/m³)
- Split: 80% train / 20% test (time-ordered, no data leakage)

## Feature engineering

Lag variables (1h, 3h, 24h), rolling averages (3h, 6h, 24h),
wind direction decomposed into sin/cos components, squared
wind speed, and temp–dew point differential.

## How to run

```bash
pip install -r requirements.txt
jupyter notebook notebooks/random_forest.ipynb
```

## Tools used

Python · pandas · scikit-learn · matplotlib · NumPy

## Authors

Jeeva Kanna Jothimani & Jessica Okereke — University of Calgary
Full project report available upon request.

