# Forecasting-ATM-Cash-Demand-in-India


## Problem Statement:
Cash demand forecasting of ATMs.

## Scope of problem:
ATMs filled with large amounts of cash may bring low transport/logistic cost but high freezing & high insurance cost. On the other hand, if banks do not have the proper mechanism to track the usage pattern, then frequent re-filling ATMs will reduce freezing and insurance cost but increase logistic cost.
Also, analysing and forecasting the cash demand will help the government to study the cash flow in the economy.

## Data Collection:
We got real world ‘ATM withdrawal value across banks’ data which is published on RBI website.
The data is dated from 01/06/2020 till 29/09/2020.
Source: https://www.rbi.org.in/Scripts/BS_PressReleaseDisplay.aspx?prid=49901



## Data Analysis:
We have decomposed the data and got to know that there is dual seasonality weekly as well as monthly. However, there is a constant trend present over time. Further, by applying Dickey’s fuller test we got to know that the data is already stationary.

## Models:
We have built our first model using Moving Average method.
For model 2, as the data is stationary, we can apply autoregressive model. But our data has seasonality present in it, so we have used Seasonal ARIMA model.
For model 3, we have used auto ARIMA to get the optimized value of the parameters p,d,q.

## Comparative Analysis:
Model 1 is made using Moving Average.
We have built other two models using SARIMAX.
In the second model, we have manually selected the value of parameters p and q based on ACF and PACF plot. And as the data is already stationary there was no need to apply differencing and so the value of parameter d is 0.
We have built second model using auto arima to get the optimized value of p and q. The value of d is same as model 2 that is ‘0’.

| Models | AIC Score | RMSE |
| :---         |     :---:      |          ---: |
| Model 1   | -     | 330.95    |
| Model 2     | 1566.86       | 461.65      |
| Model 3     | 1630.92       | 331.14      |

      	      

If we compare the metrics for each model, we see that the RMSE for moving average and auto ARIMA model is approximately same.
However, SARIMAX model considers both AR and MA properties.
Therefore, we can conclude that model 3 is performing better compared to model 1 and model 2.

Following is the comparison of forecasted values of all 3 models.

![image](https://user-images.githubusercontent.com/65092287/100250479-b8956b80-2f63-11eb-8298-934a6480366c.png)
