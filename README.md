# DATA 602 : Twitter Sentiment Analysis on Stock Market Prices

## Motivation ##
Stock price prediction is a complex and challenging task given the large number of factors involved, such as economic circumstances, political events, and others, that may affect the stock prices directly or indirectly. However, studies have shown that the stock markets are affected by the public sentiments considerably. While more people spend time online voicing their opinions, social media platforms have become a primary source of public sentiment mining. Twitter especially, has caught the interest of researchers working on analyzing public opinions and sentiments in the stock market domain, as it is a rich source of real-time information including societal and personal opinions. 

## Overview ##
In this study, potential of Twitter sentiments as a key driving element in stock price forecasting was investigated. According to our research, we found that Twitter sentiments are an influential factor in stock prices movement and prediction of some of the major companies listed on NASDAQ stock market exchange. It was also observed that the measure of ‘positivity’, ‘negativity’, and ‘subjectivity’ in tweets was significantly correlated with stock price movements thus contributing majorly towards the predictive stock price model. 

As the stock market data is a time series data having continuous information, our results indicated that the Long-Short Term Memory neural network (LSTM) model gives state-of-the-art results to forecast the stock prices using tweets sentiments and historical stock prices data. Our analysis resulted in confident predictive stock price models for Apple Inc., Amazon and Google as their stock prices showed a high correlation with Twitter Sentiments.

## Dataset ##

**Dataset Source:** Kaggle

**URLs:**
- https://www.kaggle.com/datasets/omermetinn/tweets-about-the-top-companies-from-2015-to-2020?taskId=2825
- https://www.kaggle.com/datasets/omermetinn/values-of-top-nasdaq-copanies-from-2010-to-2020

**Overview:**

The datasets were published by Mustafa et al. (2020) and they are a part of ‘Speculator and Influencer Evaluation in Stock Market by Using Social Media’ conference paper which was published in the 2020 IEEE International Conference on Big Data under the 6th Special Session on Intelligent Data Mining track.

**Data Files:**

- **Company.csv:** contains the ticker symbols of the companies. Ticker symbols are the symbols used in NASDAQ to represent a company, for example, Apple is represented by ‘AAPL’.
- **Company_Tweet.csv:** contains the unique tweet id associated with a tweet and the companies linked with the tweet id. There are a total of 3717964 unique tweet ids in this dataset.
- **Tweet.csv:** contains different attributes of tweets, e.g., tweet id, the author of the tweet, the date on which the tweet was posted, the text contained in the tweet, the number of comments and likes on the tweet, and the number of times the tweet was retweeted.
- **CompanyValues.csv:** contains the stock market data of different companies. For each day, it consists of the value of the first traded stock, the value of the last traded stock, the lowest value at which the stock was traded and the highest value at which the stock was traded.

## Methodology ##

**1.Data Preparation**
- We have focused on the analysis of aggregated tweets and not on the analysis of individual tweets because an ample number of tweets are posted in a single day. Hence aggregating those tweets, and performing sentiment analysis gives better overall sentiment values of general public’s opinion on twitter.
- First, we prepared the following types of datasets for each of the 6 companies:
  - Same Day aggregated tweets dataset: contained aggregated value of tweets and its attributes for the current day.
  - Previous Day aggregated tweets dataset: contained aggregated value of tweets and its attributes for the previous day.
  - Last 3 Days aggregated tweets dataset: contained aggregated value of tweets and its attributes for the last 3 days.
- For aggregation, we joined all the tweets in the desired period, removed the author from the dataset, and summed the comment numbers, retweets numbers and like numbers.

**2.Sentiment Analysis & Feature Engineering**
- we cleaned and pre-processed each of the above-prepared datasets, determined ‘polarity’ and ‘subjectivity’ values using TextBlob, and ‘positivity’, ‘negativity’, ‘neutrality’, and ‘compound’ values using Vader Sentiment Intensity Analyzer (SIA).
- We appended these sentiment intensity values to the original datasets.

**3.Correlation**
- we merged the sentiment values dataset and the stock market dataset to perform hypothesis testing and predictive modelling.
- Distribution graphs of the variables present in above data frames were not found to be normally distributed, which implied that ‘Spearman’ correlation coefficient had to be used in place of ‘Pearson’ correlation coefficient, to measure the degree of correlation among variables.
- Our analysis suggested that 3 companies showed strong correlation between their stock prices and twitter sentiment values. These companies were Apple (APPL), Amazon (AMZN) and Google Inc (GOOGL). 
- For these companies, it was noticed that ‘subjectivity’, ‘positivity’ and ‘negativity’ are strongly correlated with the stock prices.
- We further obtained the ‘p-values’ for these correlation coefficients to understand the significance of correlation. The p-values were fell below the significance level (alpha threshold) of 0.05 in all the cases. Hence it was proved that the correlations were statistically significant with a corresponding confidence level of 95%.

**4.Stock price prediction**
- Since we want to predict the next day’s stock price based on previous day’s stock price combined with Twitter sentiment values, our problem becomes a multivariate time series forecasting problem. 
- In other terms, we have more than one time-dependent variable, i.e., the target variable is dependent on its past values and some other variables.
- This implies that we can neither use any regressor model, nor can we use any univariate time series forecasting model like ARIMA (Autoregressive integrated moving average) or even extensions of ARIMA, such as SARIMAX (Seasonal Auto-Regressive Integrated Moving Average with eXogenous factors), which also considers seasonality in a time-series model.
- For model training, the dataset is split into 70% and 30% for the training data and testing data, respectively.
- Initially, we train a baseline Keras LSTM model that has a visible layer with 4 inputs (‘positivity’, ‘negativity’, ‘subjectivity’ and previous day stock price), a hidden layer with 50 LSTM blocks, and an output layer that makes a single value prediction (next day stock price).

**5.Model Tuning**
- We vary the LSTM model configurations to observe: 
  - the impact of increasing LSTM blocks in a hidden layer
  - effects of adding a Dropout layer.
- Afterwards, we compare the Root Mean Squared Error (RMSE) values obtained in all these models. The following LSTM model configurations for model training are implemented:
  - LSTM 1: 50 LSTM blocks (hidden layer)
  - LSTM 2: 100 LSTM blocks (hidden layer)
  - LSTM 3: 200 LSTM blocks (hidden layer)
  - LSTM 4: 50 LSTM blocks (hidden layer), 1 Dropout Layer
  - LSTM 5: 100 LSTM blocks (hidden layer), 1 Dropout Layer
  - LSTM 6: 200 LSTM blocks (hidden layer), 1 Dropout Layer

## Correlations and Significance ##

## Results ##

## Conclusions ##

## Future Scope ##

## References ##
