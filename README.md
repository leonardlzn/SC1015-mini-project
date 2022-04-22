# Stock Price Analysis and Prediction With Alphavantage Dataset
### By Li Zhaonian and Muhammad Azharuddin Bin Azhar

### content
- [Motivation](https://github.com/leonardlzn/SC1015-mini-project#motivation)
- [Data](https://github.com/leonardlzn/SC1015-mini-project#data)
- [Tools](https://github.com/leonardlzn/SC1015-mini-project#tools)
- [Analysis](https://github.com/leonardlzn/SC1015-mini-project#analysis)
- [Insights](https://github.com/leonardlzn/SC1015-mini-project#insights)
- [Machine Learning](https://github.com/leonardlzn/SC1015-mini-project#machine-learning)

---
### Motivation
Stock trading is one of the most popular investments. However it takes a lot of effort for one to be professional on stock trading. In addition, there are too many factors affecting the stock price, e.g. physical and psychological factors, rational and irrational behaviour and so on.

As references for stock prediction analysis, there is basic information like company's income, cash flow and balance sheets, and also historical data like stock price and trading volume. The interest of this project is to analyse on what is the potential data having impact on the stock prices or stock profit of different companies. Moreover, relying on the relevant data found, we intend to build a forecasting AI model that can assist on stock trading by providing stock price prediction in order to save the hectic work every trader has to do to gain profit.


---
### Data
Data used in this project is from [Alphavantage](https://www.alphavantage.co/documentation/). It provides past stock prices data up to 10 years for almost any companies, and also fundamental data of different companies like balance sheet, cash flow, earning and etc.

Use `request` library to fetch from api for fundamental data, and because of api call limit, stock prices data was not fetched from api but was downloaded as csv and then imported in the notebook. Basically all data is loaded into pandas dataframe and later usage

---
### Tools
1. pandas
2. matplotlib
3. seaborn
4. tensorflow
5. colab

---
### Data cleaning and analysis
#### cleaning
Fundamental data in quaterly basis, so in order to analyse the trend of stock prices together with the fundamental data, dataframe need to be merged by checking on matching timestamp.

Also in order to have moving average data for analysis, stock prices row data need to undergo dataframe built-in method `roll` and `shift` so that in almost all data row, there will be a data colume that contains the moving average stock price(same technique for the stock trading volume moving average).

#### analysis
The main focus of the project is to find out data that is relevant to changes of stock prices, hence we mainly uses linear plot for viewing the trend of the data and also pairplot and heatmap for finding the correlation of data.

Three main types of date were analysed, 

Firstly, stock prices of companies which are competitors to each other were plot for checking on the trend mapping. and then correlation heat map was drawn to find out the relation of different companies' stock prices.

Secondly, fundamental data was used to plot the correlation heat map with the close price

Lastly, moving average of stock prices of different number of days was plot with the stock price in terms of linear stock price graph and correlation headmap.

---
### Insights

analysis of Fundamental data in our findings did not show a correlation to a good extent with the stock price, so we conclude that it is not suitable to be used for stock prediction model training. However out result showed that stock price of a company can be affected by the competitors's stock price, but not as drastical compared to the company's past stock price data. Moreover, competitors' data might not be always available, hence we concluded that past stock price data has the highest relevance on affecting current and future stock price and should be a good choice for stock prediction model training.

---
### Machine Learning
