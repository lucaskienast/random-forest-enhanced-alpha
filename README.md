# Algotrading Random Forest enhanced alpha
In this project, random forest is used to combine signals for enhanced alpha. This includes solving the problem of overlapping samples. This project uses the end of day from Quotemedia and sector data from Sharadar.

## Installation
Use `git clone` to get a copy of this repository.
```
$ git clone https://github.com/lucaskienast/algotrading_random_forest_enhanced_alpha.git
$ cd algotrading_random_forest_enhanced_alpha
```

## Method
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

## Results
Accuracy achieved:
- train : 0.5141017391753594
- oob : 0.511164730330967
- valid : 0.5086740848732072

Despite the significant differences between the factor performances in the three sets, the AI APLHA is able to deliver positive performance.
