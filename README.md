# Trading Project
This GitHub repository will be used to host project files implementing trading strategies in various programming models along with data science and machine learning techniques.

The goal of this project is to **automate Forex trading of EURUSD**. For this we would need to identify a trading platform and trading strategy that drives the trading decisions.

## Trading Platform

We have choose [OANDA](https://www.oanda.com) Trading platform and will be using their API for executing forex trading. In order to connect to the API, you need to have at minimum a practice account with Oanda. Once logged in to you account, you can create an API token and can copy your account number. These are expected to be stored in a configuration file, with name oanda.cfg, for instance, as follows:

    [oanda]
    account_id = XYZ-ABC-...
    access_token = ZYXCAB...
    account_type = practice (default) or live

For security reasons, this file has dummy values.

## Trading Strategy

[Simple Moving Average (SMA) crossover](https://www.schwab.com/learn/story/understanding-simple-moving-average-crossovers) strategy is used to evaluate the market trend and make buy/sell decisions based on the outcome. SMA crossovers are potentially helpful in identifying when a trend might be emerging or when a trend might be ending. 

**Trading Rules:**

 - If SMA 50 crosses above the SMA 200, this can be viewed as an indicator for further price increases (buy signal)    
 - If SMA 50 crosses below the SMA 200, this can be viewed as an indicator for further price decreases (sell signal)

**Trading Positions:**

 - Buy means taking a long position (+1) 
 - if short selling is
	 - allowed/desired, Sell means taking a short position (-1) not
	 - allowed/desired, Sell means taking a neutral position (0)

**Bollinger Band Analysis**
A Bollinger Band consists of a middle band (which is a moving average) and an upper and lower band. These upper and lower bands are set above and below the moving average by a certain number of standard deviations of price, thus incorporating volatility. The buy and sell decisions can be taken whenever middle band crosses the upper or lower bands. Our analysis is primarily based on closing price and we will test Long-Short Strategy. 

A strategy that has profitable outcomes in both back testing and forward testing scenario is considered a successful.
