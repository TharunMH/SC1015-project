# Welcome to Numeric-Prediction of food prices via their commonly associated factors

## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on investigating the relationship between food prices and factors commonly thought to influence it, such as crude oil prices, inflation or fertilizer prices. If these relationships do exist, can they be used to predict food prices ? For a detailed walkthrough, please view the source code in order from 
1. Problem Formulation & Data Prep
2. Exploratory Data Analysis (1)
3. Machine Learning (1)
4. Exploratory Data Analysis (2)
5. Machine Learning (2

## Contributors
- Stanley Benjamin Yukon - Data gathering from Yahoo Finance, Data Extraction, Preparation and Cleaning, Elementary Data Analysis & Visualization.
- Peter Loh Jun Xin  - Elementary Machine Learning using Linear Regression. Helping keep the project on track. Final Presentation.
-  Tharun Mathialagan - Advanced Data Analysis using Granger Causality test. Advanced Machine Learning using XGBoost model.

## Problem Definition
1. Do the commonly held beliefs about what affects food prices hold true ? ( E.g Are Food Prices positively correlated with Oil Prices ? )
  
2. If relationships between Food Price and other variables can be established, can we predict Food Price using those variables ?

## Models Used
1. Linear Regression
2. Granger Causality
3. Extreme Gradient Boosting (XGB)

## Conclusion 
The positively correlated relationships between Crude Oil/Nat Gas and Food prices were the strongest.
        Linear Regression    XGB
Crude  :                      0.683       

Nat Gas:                      0.

The relationship between Fertilizer prices and Food prices was positively correlated but unexpectedly weak.

It is possible to predict food prices using other variables but ???

?????

## What did we learn from this project ?
1. How to extract information from the internet, specifically Yahoo Finance.
2. How to convert said data into a CSV file.
3. Handling imbalanced datasets by getting rid of NULL Values.
4. How to apply the Granger Causality test on time series to check how "temporally" related they are.
5. How to use XGB to predict values of one time series using another.

## References
- https://xgboost.readthedocs.io/en/stable/python/python_intro.html
- https://stats.stackexchange.com/questions/55465/step-by-step-example-of-predicting-time-series-with-arimax-or-armax-model
- https://www.analyticsvidhya.com/blog/2021/09/gradient-boosting-algorithm-a-complete-guide-for-beginners/
-
-
-
-
-
-
-

