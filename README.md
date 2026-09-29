# Share Market Data Analysis and Fraud Prediction Using LSTM Networks

## Team Members

- Samyuktha S — 727624BAM049
- Marrish Hariharan R — 727624BAM050
- Jayaguru R — 727624BAM051
- Sowndarya Sree T — 727624BAM052

## Project Overview

This mini project analyzes historical stock market data and uses a Long Short-Term Memory (LSTM) neural network to predict stock closing prices. It also identifies potentially suspicious market activity using unusual price movements and trading volume patterns.

## Objectives

- Analyze historical stock market data.
- Preprocess and visualize stock price and trading-volume data.
- Predict stock closing prices using an LSTM model.
- Evaluate the LSTM model using MAE, MSE, RMSE, and R².
- Identify potentially anomalous market activity using price returns and trading volume.

## Dataset

The project uses historical stock market data containing:

- Date
- Open
- High
- Low
- Close
- Volume
- Company Name

For the LSTM implementation, AAPL historical stock data was selected.

## Methodology

| Stage | Process |
|---|---|
| **1. Dataset** | Kaggle Stock Market Dataset |
| **2. Preprocessing** | Date conversion, sorting, and missing-value handling |
| **3. Exploratory Data Analysis** | Closing price, daily returns, and trading volume analysis |
| **4. Feature Engineering** | Daily Return, Volume Change, and 20-Day Volatility |
| **5. LSTM Prediction** | 60-day sequences → Min-Max Scaling → LSTM Model → Next-Day Price Prediction |
| **6. Anomaly Detection** | Return and volume thresholds → Potential Anomalous Activity |
| **7. Evaluation** | MAE, MSE, RMSE, and R² Score |
| **8. Final Results** | Price Prediction and Potential Anomaly Analysis |

## LSTM Model

The LSTM model uses the previous 60 trading days to predict the next closing price.

### Architecture

- LSTM — 50 units
- Dropout — 20%
- LSTM — 50 units
- Dropout — 20%
- Dense — 25 neurons
- Output — 1 neuron

The model uses the Adam optimizer and Mean Squared Error loss function.

## Model Results

The trained LSTM model was evaluated on the test dataset using four standard regression metrics.

MAE       : 2.5331
MSE       : 10.8840
RMSE      : 3.2991
R² Score  : 0.9198

The actual and predicted closing-price curves show that the LSTM model follows the overall trend of the AAPL stock price during the test period.

## Anomaly Detection

Potentially suspicious market activity was identified using:

- Daily Return
- Volume Change
- 20-Day Volatility

A 95th-percentile threshold was used for daily return and trading volume. Days exceeding both thresholds were flagged as potential anomalies.

### Anomaly Detection Results

Potential anomalous days : 20
Normal days              : 1,219
Potential anomaly rate   : 1.61%
Return threshold         : 2.87%
Volume threshold         : 112,841,865

These anomaly flags indicate unusual market behaviour and should not be interpreted as confirmed cases of financial fraud.

## Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- TensorFlow / Keras
- LSTM

## Project Files

- Share_Market_LSTM_Fraud_Prediction.ipynb — Complete implementation notebook

## Conclusion

The project demonstrates the use of LSTM networks for stock-market time-series prediction and statistical anomaly detection for identifying unusual market activity.
