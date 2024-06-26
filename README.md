# Welcome to Numeric-Prediction of food prices via their commonly associated factors

## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on investigating the relationship between food prices and factors commonly thought to influence it, such as crude oil prices, inflation or fertilizer prices. If these relationships do exist, can they be used to predict food prices? 
For a detailed walkthrough, please view the source code in order from 

1. Problem Formulation & Data Prep
2. Exploratory Data Analysis (1)
3. Machine Learning (1)
4. Exploratory Data Analysis (2)
5. Machine Learning (2)

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

The following is the explained variance values of the respective variables when used in a linear regression model as predictors to response variable Food prices 
Variable      Linear Regression (Explained variance)
Crude oil    :0.566       

Natural Gas  :0.555

Fertilizer   :0.371

Gold         :0.305

Tesla        :0.293

Berkshire    :0.123

The closer the explained variance value is to 1, the more indicative that the linear regression model made using the explained variance value has good fit and high predictive accuracy
The relationships between Crude Oil/Natural Gas and Food prices were the strongest as shown by model's explained variance values.
The relationship between Fertilizer prices and Food prices was weakly correlated.
Gold and Tesla strangely share similar explained variance values which may be indicative of possible issues with using linear regression on time series data as Tesla was meant to be a negative control yet, its moderately high explained variance warrants validation on whether linear regression is a good model for our time series data prediction.

We must take note that time series data consists of the following properties:
Trends are the overall rate of change in a time series data which is what we seek to reveal and compare through analysis.
Seasonality which is a property of certain time series data such as our stocks and futures data where there are recurring patterns of change that occurs throughout its the interval of data collection such as seasons affecting food prices and consumer purchasing habits.
Stationarity is the property of time series data where it is not affected by seasonality.
The property of a single value can be related to its previous value (also known as lagged value). This can be taken into account using autocorrelation.


The Granger Causalitytest is used to test for "Granger Causality" or the degree to which two time series datasets are temporally related.
A simple linear regression would not produce a reliable correlation value as changes in one time series may not immediately affect the other. (add on) The P-value obtained from a Granger Causality test allows us to check the validiaty of the Null Hypothesis. The smaller the P-value, the more likely it is that the NULL hypothesis can be rejected.( NULL Hypothesis: There is NO correlation between the datasets.)

               Granger Causality test p-value
Crude Oil:                0.0004

Natural Gas:              0.0004

Fertiliser:               0.0011

Gold:                     0.0301

Bonds:                    0.1221

Tesla:                    0.0 (anomalous)

Berkshire:                0.0177


The Granger causality test results indicate that bonds do not significantly influence food prices, as their p-value (0.1221) surpasses the significance threshold of 0.05. However, Tesla's anomalous p-value of 0.0 suggests that its influence on food prices might not be accurately captured by the test due to its non-stationary nature, likely stemming from substantial market price increases in the later half of the decade.
The other 5 predictors have a p-value of lower than 0.05, thus we can reject the NULL hypothesis that there is no relation between the variables. This suggests that these 5 predictors do have a predictive influence on food price. However, since granger causality test does not establish and true 'cause and effect' relationship, we will plug these 5 predictors and Foodsum into XGBoost, a machine learning model 

We employed XGBoost, a robust machine learning technique, to forecast forthcoming food price values by leveraging data from another time series(our predictors) with data lagging. By assessing the correlation between predicted and actual food prices, we aim to gauge the predictive power of these variables and their association with food price dynamics. (Graphs genrated and analysis in 5. Machine Leatning (2))

                   XGBoost Explained Variance
    Crude Oil:                0.68289

    Natural Gas:              0.53392

    Fertiliser:              -0.10358

    Gold:                    -0.20308

    Berkshire:               -0.00042
    
    
Above is the compiled list of explained variance for each of the XGBoost models using the different predictors. (Graphs genrated and analysis in 5. Machine Leatning (2))

Concluding from the analysis of the closeness of the actual and predicted graph of price of food (Foodsum) generated by the XGBoosted model and the explained variance, crude oil and natural gas emerge as strong predictors for food prices. However, notable limitations include plateauing predictions, negative explained variance, and reliance on proxies for key data. 

To address these:

1. Plateauing predictions may stem from inadequate features, non-stationarity, or model constraints. Recommendations include incorporating more relevant features and updating the model with improved data.

2. Negative explained variance could result from overfitting, irrelevant features, data quality issues, or inappropriate model settings. Recommendations involve reassessing data preprocessing, feature engineering, and model tuning.

3. Reliance on proxies for key data, like Foodsum and fertilizer, may introduce discrepancies. A better database representing predictors and food prices is recommended for improved accuracy.



## What did we learn from this project ?
1. How to extract information from the internet, specifically Yahoo Finance.
2. How to convert said data into a CSV file.
3. Handling imbalanced datasets by getting rid of NULL Values.
4. What are the properties of time series data.
5. What are some of the machine learning techniques used to perform numeric predictions using time series data.
6. How to apply the Granger Causality test on time series data to check how "temporally" related they are.
7. How to use XGB to predict values of one time series using another.

## References
- https://xgboost.readthedocs.io/en/stable/python/python_intro.html
- https://stats.stackexchange.com/questions/55465/step-by-step-example-of-predicting-time-series-with-arimax-or-armax-model
- https://www.analyticsvidhya.com/blog/2021/09/gradient-boosting-algorithm-a-complete-guide-for-beginners/
- https://www.berkshirehathaway.com/subs/sublinks.html
- https://www.influxdata.com/what-is-time-series-data/#:~:text=Time%20series%20data%20is%20unique,questions%20about%20it%20over%20time.
- https://towardsdatascience.com/stationarity-in-time-series-analysis-90c94f27322
-
-
-
-

