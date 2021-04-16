## Download the anonymized dataset describing persons.csv from a West African county and import it into your PyCharm project workspace (right click and download from the above link or you can also find the data pinned to the slack channel). First set the variable wealthC as your target. It is not necessary to set a seed. ##

To set up for this lab I imported the data and then dropped the na, which was about 70-80 data points, which should not affect the outcomes. After I checked the data types I changed age and edu to int. I set the features for X, dropping wealthC and wealthI and setting these as the target for the following regressions. 

``` 
person = pd.read_csv('persons.csv')
person.dropna(inplace=True)

person['age'] = person['age'].astype(int)
person['edu'] = person['edu'].astype(int)

X = person.drop(["wealthC", "wealthI"], axis = 1)
# y = person.wealthI
y = person['wealthC']
``` 

## WealthC ##

linear regression and compute the MSE:

Linear regression MSE: 0.44281007841525455

Standardize the features and again compute the MSE:

Linear regression MSE: 0.4428133309487589

Compare the coefficients from each of the two models:

ridge regression:

For ridge regression I started by using a_range = np.linspace(0, 120, 110) to try and find a starting point from there I kept narrowing what my range should be in order to find the best results. In the end my best outcome would have to be the range: a_range = np.linspace(72, 76, 20) with my results being:

Optimal alpha value: 72.21053
Training score for this value: 0.73584
Testing score for this value: 0.73521

![ridge1](wealthcridge.png)

lasso regression:

## WealthI ##

linear regression and compute the MSE:

Linear regression MSE: 1750276834.9304745

Standardize the features and again computer the MSE:

Linear regression MSE: 1750287416.4378276

Compare the coefficients from each of the two models:

ridge regression:

lasso regression:

## Which of the models produced the best results in predicting wealth of all persons throughout the smaller West African country being described? ##
