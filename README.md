# Bike-Sharing-Demand-Prediction

![Python](https://img.shields.io/badge/python-3670A0?style=plastic&logo=python&logoColor=yellow)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=plastic&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=plastic&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=plastic&logo=Matplotlib&logoColor=black)
![Seaborn](https://img.shields.io/badge/Seaborn-%23ffffff.svg?style=plastic&logo=Matplotlib&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=plastic&logo=scikit-learn&logoColor=white)

## Introduction

A **bike-sharing** system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share system allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system. 

## Problem Statement 

A US bike-sharing provider has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

In this project, we will try to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. We will use statistical testing to analyze the key factors and build a regression model to predict the demand and provide insights so that they can prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

## Business Goals

Understand the factors affecting the demand for these shared bikes in the American market.
* Which variables are significant in predicting the demand for shared bikes? How well those variables describe the bike demands?
* Build a ML Regression model to predict how the demand vary with different features. 
* Deliver the recommendations to the management so they can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. 

## Initial Questions
- Which variables are associated with demand?
- How does the weather and temperature affect the demand?
- In which months demand is more?
- Is the demand more during weekdays or weekend and during holidays? 

## Data Dictionary

- instant: record index
- dteday : date
- season : season (1:spring, 2:summer, 3:fall, 4:winter)
- yr : year (0: 2018, 1:2019)
- mnth : month ( 1 to 12)
- holiday : wheather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
- weekday : day of the week
- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
+ weathersit : 
	- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
	- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
	- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
	- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
- temp : temperature in Celsius
- atemp: feeling temperature in Celsius
- hum: humidity
- windspeed: wind speed
- casual: count of casual users
- registered: count of registered users
- cnt: count of total rental bikes including both casual and registered

## Process 
### 1. Data Source
  - [Link](https://www.kaggle.com/competitions/bike-sharing-demand/data)
    
### 2. Data Understanding 
  * Importing and Inspecting the data
  * Visualizing numerical and categorical variables and finding the insights
 
### 3. Data Preparation
  * Encoding
  * Data splitting 
  * Scaling the variables 

### 4. Training and Building the model using statsmodels 
  * Used Recursive Feature Elimination to find the most significant features 
  * Applying Ordinary Least Squares to fit the training data
  * Further eliminating variables using Variance Inflation factor, t - statistics and it's p-values. 
  * Finalising the model with VIF less than 5 and p-value < 0.05.
  
### 5. Residual Analysis 
  * Validating the assumptions of error terms having normal distribution with zero mean and they follow homoscedasticity. 
  
### 6. Model Predictions 
  * Making the predictions on test data using the final model.
  
### 7. Model Evaluation 
  * R-squared and Adjusted R-squared were calculated. 
  * RMSE was calculated to check the performance of the model. 
 
## Key Findings 
- Statistically Significant features that affect the target variable. 
  * Temperature 
  * Year
  * Winter season
  * Summer season
  * Month of August, September and October
  * Misty/Cloudy or light rain/snow weather
  * Holiday
  * Windspeed
  * Humidity

- From the visualization of categorical variables we see that count is highest during fall season and then during summer and winter. We see less demand in the season of spring.
- particulary in the months of June, July, August and September. 
- We also see that in the year 2019 the count has increased tremendously, we can say that increase in popularity might have been the reason for it.
- The demand is also more when there is clear weather in the sky and then during misty/cloudy weather.  
