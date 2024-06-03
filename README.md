# FX-LSTM
Utilizing LSTM CNN to predict time-series data for EUR_USD foreign currency conversion rates


# Problem Description
In this project, I aim to predict the hourly closing prices of the EUR/USD currency pair using a Long Short-Term Memory (LSTM) neural network. Accurate prediction of currency exchange rates is a critical tool for forex traders, financial analysts, and investors to make informed decisions. 
The dataset includes various features such as opening, high, low, and closing prices along with technical indicators derived from price data, like SMA, RSI, and MACD. By leveraging these features and the LSTM model's ability to capture time-series data analysis, we aim to achieve robust and reliable predictions.

# EDA Procedure
The Exploratory Data Analysis (EDA) involved inspecting the dataset to understand its structure, distribution, and key characteristics. 
- We visualized the closing prices over time to identify trends and patterns. 
- Added technical indicators such as Simple Moving Averages (SMA), Relative Strength Index (RSI), and Moving Average Convergence Divergence (MACD) to enhance the dataset for Hyperpareter Tuning Features. 
- Summary statistics were computed, and missing values were handled by dropping rows with NaN values resulting from the rolling window calculations for the indicators.

### Note:
- Most of the data preprocessing and collection is from OANDA API and captured using the addition scripts('collect_historical_data.py)
- **defs.py** template included. Need to create credentials for OANDA API and get your own acccess code

```python
# Placeholder definitions. Replace with actual values.
OANDA_URL = "https://api-fxpractice.oanda.com/v3"
ACCOUNT_ID = "your_account_id"
SECURE_HEADER = {
    "Authorization": "Bearer your_access_token"
}

```

# Analysis
The analysis phase involved building and training an LSTM model for time series prediction. We first scaled the data and created sequences of 24 hours as inputs for the model because I wanted to essentially predict the next 24 hour price data. The LSTM network was designed with two layers, each followed by a Dropout layer to prevent overfitting.
## Hyperparameterized Model (2nd iteration)
I employed new technical indicators and deployed a new model with additional layers and dropout layers. I ran into computaiton resourcing issues with Google Colabs but further development of this model is in plan for the future


# Discussion/Conclusion/Results
The results of the inital model gave prediction prices for the next 24 hour price points for the EUR_USD currency pair. However, in foresight I should have ran this on a day with tradeable data. Since I ran and trained the model over the weekend it prevented me from geting the actual price to compare performance. The intial model needs to be further developed because the Fiancial currency markets are much more volatile to be accurately predicted using price data alone. With the further development I plan to implement
- Sentiment Analyis
- Fine-Tuned Candlestick analysis and Price Action
- Risk Management Systems
- Extensive Backtesting Automations


In conclusion, the LSTM model could be a profitable algorithm to be used to predict the hourly closing prices of the EUR/USD currency pair and other Currency pair markets. It shows it's promises in this use case for me by demonstrating the model's capability to capture temporal dependencies in time series data. The addition of more advanced technical indicators will further enhanced the model's performance and layering in other models developed will attribute to higher accuracies in theory. While the results are promising, further improvements will be made by incorporating more features, fine-tuning hyperparameters, and exploring other deep learning architectures. 


