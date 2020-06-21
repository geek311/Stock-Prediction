# Stock-Prediction

Accurately predicting Stock Prices has been a long-standing problem that mankind has tried to solve. While there is no model that exists, which can accurately and with complete certainty predict all stock prices accurately, yet this is one of the most interesting problems that can be dealt with by using Machine Learning and Neural Networks. Given the past historical
   
performance of stocks, this project tries to solve of the problem of predicting the stock prices in the market as accurately as possible. The problem is replicable and quantifiable.

#### In this LSTM model, I will be using tech stocks to predict the prices for 'AAPL', 'GOOG', 'AMZN' and 'MSFT'

## Environment Requirements
This project was developed in Amazon Sagemaker with a conda_tensorflow_36 kernel and needs the Pandas datareader packages

## Datasets and Inputs

The datasets and inputs used in this project will be from Alpha Vantage and S&P 500 Full dataset with 10 Years of Open/Close/Low/High/Volume data.
#### (1)	Yahoo Finance – To get the historical and latest stock prices. Using pandas-datareader (a pandas extension with built-in web-scraping features), I have scraped the stock prices of last 10 years

#### (2)	Alpha Vantage – At the outset, an API key will be required, which we will be obtained for free at the above link. After that, the API key will be assigned to the api_key variable.

Alpha Vantage APIs are grouped into four categories: (1) Stock Time Series Data, (2) Physical and Digital/Crypto Currencies (e.g., Bitcoin), (3) Technical Indicators, and (4) Sector Performances. All APIs are real time: the latest data points are derived from the current trading day. This project will be using the Stock Time Series Data.

#### (3)	S&P 500 Full dataset  - Data is downloaded for S&P 500 stocks into a “Stocks” folder. Later this data will also be uploaded in a folder in S3 bucket which the model can use.


For each stock, the inputs multiple metrics - opening price (Open), highest price the stock traded at (High), how many stocks were traded (Volume) and closing price adjusted for stock splits and dividends (Adjusted Close) . 

#### Characteristics of input datasets :
•	Open: Opening stock price of the day

•	Close: Closing stock price of the day

•	High: Highest stock price of the data

•	Low: Lowest stock price of the day

•	Volume : Volume of shares tracded on a day

•	Adjusted Close : the closing price that has been amended to include any distributions and corporate actions that occurred at any time prior to the next day’s open



Since this goal is to predict future stock prices through a Long Short-Term Memory (LSTM) method, it is important to understand the historical performance of the stocks, the pattern and risk factors and then predict the stock movement in the future. Hence, the above two datasets will provide ample data points we require to train, test and evaluate the model

## Note - Input Data
2 datasets are important :
(1) Data in data/stocks folder containing stocks with 10-year stock price history

(2) "goog.csv" - Googlestock price history used in Benchmark Model for comparison. For Benchmark analysis, I got this dataset from Yahoo Finance

## Solution Statement
To solve this problem, I am using recurrent neural network.  I will be using Long Short-Term Memory as the model - LSTMs are an enhanced version of recurrent neural networks (RNNs). LSTMs are a type of RNN that remember information over long periods of time, making them better suited for predicting stock prices. The stock that the user selects will be the target. The model will be trained and used to predict the closing price stock price of the chosen stock using LSTM.

## Implementation
The solution has been divided into the following parts :
1) Determine change in price and volume traded of the stocks, over time
3) Simple Moving Average of the input stocks
4) Determine correlation between different stocks – This is done to find clusters of stocks that appreciate or decline together or have similar market factors that impact them
5) Determine risk factors by analyzing average daily returns of the stocks and correlation. This is to determine the risk of the portfolio
6) Predict closing stock price and stock price movement of any given stock. 
7) Evaluate model performance

#### stock-market-prediction.ipynb has the main code 

References :
https://en.wikipedia.org/wiki/NASDAQ
https://en.wikipedia.org/wiki/New_York_Stock_Exchange 
http://www.investopedia.com/terms 
https://en.wikipedia.org/wiki/Root-mean-square_deviation
https://en.wikipedia.org/wiki/Coefficient_of_determination 
http://scikit-learn.org/stable/modules/model_evaluation.html 
https://www.kaggle.com/wiki/RootMeanSquaredError
https://www.kaggle.com
