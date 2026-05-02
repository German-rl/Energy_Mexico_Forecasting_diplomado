## ⚡ Electricity Generation Forecasting in Mexico using RNN and LSTM

This project develops time series forecasting models to predict electricity generation in Mexico using deep learning techniques, specifically Recurrent Neural Networks (RNN) and Long Short-Term Memory (LSTM) models.

The analysis is based on historical data from the Secretaría de Energía and aims to provide a data-driven approach to understand and anticipate energy generation patterns.

## Objective

To forecast monthly electricity generation in Mexico by capturing key temporal patterns such as:

Seasonality
Trend
Structural changes (e.g., COVID-19 impact)

## Dataset
Source: Mexican Energy Information System (SIE)
Period: 2002 – March 2025
Granularity: Monthly generation by state
Size: ~29,000 records
## Data Processing
Conversion to tidy format
Transformation into a monthly time series
Handling missing values (domain-informed imputation)
Aggregation at national level

## Exploratory Data Analysis (EDA)

Key findings:

📈 Increasing trend in electricity generation (2000–2012)
⚖️ Stabilization in recent years
📉 Noticeable drop during COVID-19 with recovery phase
🔁 Clear yearly seasonality:
Peaks: summer months
Lows: winter months

## Modeling Approach

Multiple deep learning models were implemented and compared:

  ### Architectures
RNN (Recurrent Neural Network)
LSTM (Long Short-Term Memory)
  ### Forecasting Strategies
Single-step: Predict one time step ahead
Multi-step: Predict multiple future time steps
  ### Pipeline
Data normalization
Sliding window generation
Time-based train/test split (past → future)
Model training and evaluation on unseen data

## Results
 ### Model Comparison
 
| Method               | MAE         | RMSE        | MAPE      |
| -------------------- | ----------- | ----------- | --------- |
| Multiple Step RNN    | 3,319,318   | 3,763,270   | 15.32%    |
| Multiple Step LSTM   | 2,493,196   | 2,782,009   | 11.61%    |
| Single Step RNN      | 1,334,948   | 1,591,747   | 6.47%     |
| **Single Step LSTM** | **805,058** | **983,441** | **3.97%** |


LSTM models consistently achieve lower error, highlighting their ability to capture long-term temporal dependencies and mitigate vanishing gradient issues.
Single-step models provide significantly better accuracy.
Multi-step models accumulate error over longer prediction horizons.
The Single-step LSTM achieved the best performance:
  ### MAPE ≈ 3.97%
### Real-World Applications
This type of forecasting model can support:
  Electricity generation planning
  Resource optimization
  Renewable energy integration
## Tech Stack
Python
Pandas / NumPy
Matplotlib / Seaborn
TensorFlow / Keras
Statsmodels
Future Work
### Benchmark against classical models (ARIMA, naive baseline)
Incorporate exogenous variables:
Weather
Energy demand
Fuel prices
Explore advanced architectures (GRU, Transformers)
Implement walk-forward validation
Deploy as an API or dashboard

## Conclusion

### This project demonstrates that deep learning models, particularly LSTM, can effectively model the temporal dynamics of electricity generation in Mexico, achieving low forecasting error even with real-world variability.

It also highlights the importance of:

Selecting appropriate forecasting strategies
Comparing multiple models
Understanding the domain context
