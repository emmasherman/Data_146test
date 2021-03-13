## Download the dataset charleston_ask.csv and import it into your PyCharm project workspace. Specify and train a model the designates the asking price as your target variable and beds, baths and area (in square feet) as your features. Train and test your target and features using a linear regression model. Describe how your model performed. What were the training and testing scores you produced? How many folds did you assign when partitioning your training and testing data? Interpret and assess your output. ##

The first model that I created and tested did not perform well. The training scores that I got were: 

Training: 0.019
Testing: -0.024

Since a perfect model would have the result of 1, this model did not perform well since these outcomes show that are far from 1. 
I used 14 folds when running my model. I chose to do 14 folds because there are approximately 715 data entries so there approximately 50 pieces of data in each fold for each fold. I chose this bin size because this way the splits are not too big but all not too many splits because more splits will make the testing be smaller and therefore the results will be less consistency. 

## Now standardize your features (again beds, baths and area) prior to training and testing with a linear regression model (also again with asking price as your target). Now how did your model perform? What were the training and testing scores you produced? How many folds did you assign when partitioning your training and testing data? Interpret and assess your output. ##

After running the first model I standardized the data before running the training and testing with a linear regression model again. I used Standardized from sklearn as seen here: 

``` 
from sklearn.preprocessing import StandardScaler as SS
ss = SS()
homes_form = ss.fit_transform(homes)
```

After processing the data I ran the model again with the standardized data and got:

Training: 0.019
Testing: -0.034

There is not much change from the oringial model in regards to the outcome. The model did not perform well. For this run of the model, like the first question, I used 14 folds to try and get the most consistent outcome as possible. 

The performance of all of these models were not strong and this could be due to the fact that beds, baths, and sqft might not be good predictive indicators for the asking price of a house. 

## Then train your dataset with the asking price as your target using a ridge regression model. Now how did your model perform? What were the training and testing scores you produced? Did you standardize the data? Interpret and assess your output. ##

By adding a degree of bias to the regression estimates, ridge regression reduces the standard errors.

Not Standardized: 

Optimal alpha value: 89.899
Training score for this value: 0.019
Testing score for this value: 0.011

Standardized: 

Optimal alpha value: 82.828
Training score for this value: 0.019
Testing score for this value: 0.014

## Next, go back, train and test each of the three previous model types/specifications, but this time use the dataset charleston_act.csv (actual sale prices). How did each of these three models perform after using the dataset that replaced asking price with the actual sale price? What were the training and testing scores you produced? Interpret and assess your output. ##

## Go back and also add the variables that indicate the zip code where each individual home is located within Charleston County, South Carolina. Train and test each of the three previous model types/specifications. What was the predictive power of each model? Interpret and assess your output. ##

## Finally, consider the model that produced the best results. Would you estimate this model as being overfit or underfit? If you were working for Zillow as their chief data scientist, what action would you recommend in order to improve the predictive power of the model that produced your best results from the approximately 700 observations (716 asking / 660 actual)? ##
