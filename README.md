# Welcome to Numeric-Prediction of food prices via their commonly associated factors

##About
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

## Conclusion 
The relationship between Crude Oil/Nat Gas and Food prices was the strongest.

?????




There are no SINGULAR, GLOBAL prices for food or many other commodities. We will now need to get proxies for the price of real world items.

1. Crude oil can be tracked via Crude Oil prices [CL=F]
2. Natural Gas can be tracked via Natural Gas prices [NG=F]

3. Inflation Rates. There is no singular GLOBAL inflation rate but it can be approximated using the trade price of Gold [GC=F]. If inflation is high, gold prices are likely to increase as well; due to people seeking to use Gold as a hedge.

4. Bond Prices can be approximated using the US 5-Year Treasury Bond [ZF=F]
   
6. RANDOM VARIABLE ( Berkshire Hathaway ) [BRK-A]
7. RANDOM VARIABLE ( Tesla ) [TSLA]
( Random Variables are required to know what a "bad" correlation looks like )

8. Part one of approximating "Food Prices" - Rough Rice Futures [ZR=F]
9. Part two of approximating "Food Prices" - Wheat Futures [ZE=F]

10. Fertilizer Prices. There is no singular GLOBAL fertilizer price but it can be approximated using the trade price of fertilizer manufacturing companies. We chose [SQM] based in Chile.




