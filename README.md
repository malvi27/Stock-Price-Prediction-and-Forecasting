# Stock-Price-Prediction-and-Forecasting
LSTM Models for predicting and forecasting the stock price predictions
Model1 : Using MinMaxScalar
Dataset Collected from Tiingo.
Sign in to Tiingo, and afterward visit https://api.tiingo.com/account/token and you will see your token
The split is done in 65:35 ratio for training and testing.

################################################################################################################################################################

Model2 : Instead of MinMaxScaler, here we use StandardScaler. We scale the train set to have mean 0 and var 1, and then whenever we do prediction on dev or test set we scale the previous N values to also have mean 0 and var 1 (ie. use the means and variances of the previous N values to do scaling. We do this for both feature columns and target columns)
Here we split 3 years of data into train(60%), dev(20%) and test(20%)
Given prices for the last N days, we do prediction for day N+1
We have tuned 'N' to use as features
