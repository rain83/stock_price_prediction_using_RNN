# [Stock Price Forecasting with LSTM]

## Project overview:
The project uses a Long Short-Term Memory (LSTM) neural network to forecast stock prices based on historical adjusted closing prices. 
The model is trained using past stock prices and aims to predict future price movements.

## Data:
The stock price data is fetched from Yahoo Finance (`yfinance`) and includes:
- **Ticker(s):** By default, the project is done on AMZN stock prices. A variation of the code to apply to a list of tickers is on the way.
- **Date Range:** 2016-01-01 to 2024-01-01
- **Feature Used:** Daily adjusted closing prices

## Model:
The model is built using TensorFlow/Keras and consists of:
- **Input:** 3 previous days' adjusted closing prices
- **LSTM Layer:** 64 units
- **Dense Layers:** Two fully connected layers with 32 neurons (ReLU activation)
- **Output Layer:** Single neuron for next-day price prediction

## Training and Evaluation
### Train-Validation-Test Split
The dataset is divided into:
- **Training Set:** 80%
- **Validation Set:** 10%
- **Test Set:** 10%

### Visualisation
- Training, validation, and test set predictions are plotted against the actual prices.
- The model is optimized using Mean Squared Error (MSE) and Mean Absolute Error (MAE).

## Limitations:
- The model is too autoregressive, it uses **only** past prices for predictions.
- It does **not** predict from truly unknown data (i.e., future real-world stock prices), as the test set is derived from historical data; although the learning is completely disjoint from the test set, the use of past prices leaks a lot of test data into the predictions.

## Suggestions for improvements:
- Incorporate **volume traded** as an additional feature.
- Incorporate **technical indicators** (moving averages, RSI, MACD, etc.).
- Incorporate **macroeconomic indicators**, like yield curve data.
- Use **news sentiment analysis** to capture market reactions (highly prospective in an environment with a lot of noise traders).
- Test the model on real future data to assess practical performance.

## contributors
- [Reetom Ghosh]
