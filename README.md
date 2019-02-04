# **Project: AirBnB Price Prediction**
### In this project a  Machine Learning algorithm has been developed and implemented, that helps costumers to predict the price of AirBnB listings in major U.S. cities with respect to different parameters that affect the pricing of the houses, like city, number of rooms, location, property type, etc.
### The dataset and other details can be downloaded from kaggle website: https://www.kaggle.com/rudymizrahi/airbnb-listings-in-major-us-cities-deloitte-ml 

## Overview
**The goals / steps of this project are the following:**
1. Data cleaning (i.e. handling missing data, etc)
2. Data visualization
4. Data preprocessing
3. Feature Selection
4. Implementing Regression analysis with 10-fold cross validation
5. Performing Grid search to find best parameters for above models
6. Predict the pricing using test set
    
[//]: # (Image References)

[image1]: ./plot1.png
[image2]: ./plot2.png
[image3]: ./plot3.png

## Brief explanation of each step

### Data Cleaning
- Missing values were found in bedrooms, beds, host_has_profile_pic, host_identity_verified, host_since, bathrooms, zipcode, neighbourhood, thumbnail_url, last_review, first_review, review_scores_rating, host_response_rate.
- For bathrooms, bedrooms, beds, review_scores_rating filled empty places with 'zero'.
- For host_has_profile_pic, host_identity_verified the data available is 't' or 'f', so converting it into '1' or '0' and then filling empty places with 'zero'.
- For neighbourhoood, thumbnail_url the values are in string format so filling empty places with 'Unknown'.
- For host_response_rate the values are available in % so removing the % symbol and keeping the values. And then filling empty places with 'zero'.
- For last_review, first_review, host_since the values are in date format, so replaced the empty places with '00-00-00'.
- For zipcode, I have used uszipcode.Zipcode, uszipcode.SearchEngine library that provides with zipcode values for available longitudes and latitudes.

### Data Visualization
- Integer Pricing per City: Plot 1 explains about Average pricing per city. From Bar Graph, San Francisco has Highest Price and Chicago has Lowest Price among NewYork, DC, Los Angeles,  Boston, San Francisco and Chicago.
![alt_text][image1]
- Average pricing for Property Type w.r.to City: Plot 2 explains the relation between, Property Type-City-Price. We can obtain different variations in prices as per Property Type and its Location.
![alt_text][image2]
- Price variation for Property Type as per number of Accommodates: From this plot we can identify how prices varies for different properties and how number of accommodates affect it.
![alt_text][image3]

### Feature Selection
PCA feature selection technique was used for Model Implementation.
I also tried doing stepwise forward feature selection, since it was consuming a lot of time did not wait for it complete its entire action of selection. But as per plot for stepwise forward feature selection, the Standard Error remains constant after selecting 20 features.

### Model Implementation
Three different rigression models were utilized to test the prediction of the prices:
- Linear Rigression
- Ridge Rigression
- Lasso Rigression

### Grid Search Technique
The grid search is a technique to find the best parameters for your model. It performs an exhaustive search over the hyperparameter search space to get the best settings.

## Result
From all the three utilized models i.e. Linear, Ridge and Lasso. Lasso Regression provided MSE of 0.22 on test data set which was better than Linear Regression and close to Ridge Regression. This was because, Lasso selects the only some feature while reduces the coefficients of others to zero. This property is known as feature selection and which is absent in case of ridge.
