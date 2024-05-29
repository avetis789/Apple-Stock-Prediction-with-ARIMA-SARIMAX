Predicting Apple Stock Prices

Overview:
This repository contains the code and resources for my capstone project on predicting Apple stock prices using time series analysis techniques, specifically ARIMA and SARIMAX models. The model aims to forecast daily closing prices and provide buy/sell recommendations for day traders.

About This Model:
This model includes daily Apple stock statistics, including open price, close price, and more for 10 years. If successful, the model will provide a prediction of the closing price for the given day with a recommendation to buy or sell. This will be very helpful for day traders who trade once per day. The data can be fetched via Yahoo Finance, and the necessary libraries and modules are included in the code.

Data Description:
Source: Yahoo Finance
Period: 10 years
Rows/Days: 2506
Features: Daily open, high, low, close prices, and volume
Target Variable: close
Train/Test Split: 85% train, 15% test

Research Question:
Based on the available data, can we predict daily Apple closing stock prices?

Model Practical Use:
This model is intended for day traders who trade once a day based on the predicted stock price at the close of the day. The goal is to achieve a margin of error less than 10%.

Data Analysis Insights:
Trend: The initial inspection of the daily closing prices over 10 years shows an overall upward trend in Apple stock prices, beneficial for long-term investors.

Autocorrelation: The ACF plot indicates strong autocorrelations at multiple lags, implying potential seasonality or a long-term trend.
Partial Autocorrelation: The PACF plot shows that only the first two days have a direct influence on today’s price.

Model Choice:
Given the continuous nature of the data and its autocorrelation properties, a SARIMAX model with auto-ARIMA was chosen to find the best parameters. The SARIMAX model performed better than the grid-searched optimal SARIMAX parameters.

Model Evaluation:
The model evaluation metrics indicate strong performance:
Mean Squared Error (MSE): 35.92
Mean Absolute Error (MAE): 5.18
Root Mean Squared Error (RMSE): 5.99
Mean Absolute Percentage Error (MAPE): 2.95%
R-squared (R²): 0.8874

Buy/Sell Recommendation:
The model provides buy/sell recommendations based on the comparison between the previous day’s forecast and the current day’s forecast. The forecast mimics the actual close with 90-91% accuracy. The recommendation system showed only a 9% mismatch rate, primarily when the difference in price change was less than 50 cents.

Weak Points/Shortcomings:
Error Rate: The model has a 9% error rate in variance less than 50 cents.
Recommendation Accuracy: The model's buy/sell recommendations are less accurate when the price change difference is minimal.

Conclusion:
Overall, the model performs well, explaining almost 89% of the variance in daily closing prices. The 9% error rate is considered insignificant for day traders following daily recommendations.

Next Steps:
The next step involves connecting the model to live data to make informed purchase decisions.
