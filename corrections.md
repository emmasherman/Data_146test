
```
def DoKFold(model, X, y, k, standardize=False, random_state=146):
    import numpy as np
    from sklearn.model_selection import KFold
    kf = KFold(n_splits=k, shuffle=True, random_state=random_state)
    if standardize:
        from sklearn.preprocessing import StandardScaler as SS
        ss = SS()
    train_scores = []
    test_scores = []

    train_mse = []
    test_mse = []

    for idxTrain, idxTest in kf.split(X):
        Xtrain = X[idxTrain, :]
        Xtest = X[idxTest, :]
        ytrain = y[idxTrain]
        ytest = y[idxTest]

        if standardize:
            Xtrain = ss.fit_transform(Xtrain)
            Xtest = ss.transform(Xtest)

        model.fit(Xtrain, ytrain)

        train_scores.append(model.score(Xtrain, ytrain))
        test_scores.append(model.score(Xtest, ytest))

        ytrain_pred = model.predict(Xtrain)
        ytest_pred = model.predict(Xtest)

        train_mse.append(np.mean((ytrain-ytrain_pred) ** 2))
        test_mse.append(np.mean((ytest - ytest_pred) ** 2))

        return train_scores, test_scores, train_mse, test_mse
        
 ```

## Question 17 ##

## Question 18 ##

## Question 19 ##

## Question 20 ##

## Question 21 ## 

## Question 22 ##

