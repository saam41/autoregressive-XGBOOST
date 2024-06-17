# autoregressive-XGBoost
This project extends the XGBoost algorithm to include autoregressive trees as base learner instead of traditional regression trees. Two variations of this algorithm were developed: the single-output variation, denoted as AR-XGBoost, and the multi-output variation, denoted as MOAR-XGBoost. The resulting algorithms were tested on financial time series. The two variations were coded on Python and consist of two classes, the 'leaf' class and the 'tree' class. The remaining parts of the code were used to handle the data for testing. 
## Data
The data consists of two separate data sets, both of which were downloaded from the Wharton Research Data Services. The data was collected for stocks from the ‘Electronic computers’ industry, denoted by the SIC code 3571. The first data set contains a list of daily stock prices, provided by the Center for Research in Security Prices (CRSP). The second data set presents a list of quarterly fundamentals provided by S&P Global Market Intelligence.
## AR-XGBoost
The AR-XGBoost is characterised by autoregressive trees as base learner. The autoregressive trees fit a linear autoregressive model in each leaf. The output is then piece-wise linear rather than piece-wise constant as is the case for traditional regression trees. The AR-XGBoost yields a set of coefficients in each leaf which are subsequently used to produce a single forecast (hence the single-output definition). The code can be found in 'ar_xgboost.py'.
## MOAR-XGBoost
The MOAR-XGBoost employs autoregressive trees as base learner. This algorithm fits a VAR model in each leaf which is estimated via OLS by first transorming the matrix of regressors into a block matrix. The output consists of a vector of coefficients which are then used to produce multiple forecasts (hence the multi-output definition). The code can be found in 'xgb_multi'.
