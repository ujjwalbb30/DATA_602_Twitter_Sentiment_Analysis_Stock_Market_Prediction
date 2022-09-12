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

## Correlations and Significance ##

## Results ##

## Conclusions & Future Scope ##

## References ##
