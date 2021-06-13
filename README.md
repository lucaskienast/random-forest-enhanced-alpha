# Algotrading Random Forest enhanced alpha
This is a random forest model for enhanced alpha written in Python. It works as follows:
- get stock data using `zipline`
- compute daily stock returns
- create alpha factors: 1 year momentum, mean reversion 5 day sector neutral, and overnight sentiment
- create features: stock volatility, stock dollar volume, sector, market volatility, market dispersion, and date features
- create targets using trailing 5 day return
- check if target returns are independent and identically distributed
- split data into training, validation and test data
- train random forests with different tree sizes using `sklearn.ensemble.RandomForestClassifier`
- evaluate Sharpe ratios, factor returns, and factor rank autocorrelation with `alphalens`
- create ensemble of non-overlapping trees with custom `sklearn` estimator
- train model and get accuracy on train, oob (out of bag), and valid data
- test model
