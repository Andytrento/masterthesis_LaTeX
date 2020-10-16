# Experiment and Results

<!--Structure suggested-->



## Training and test sets



<!--What is generability and why it matters?-->

We split the dataset into 80 listings (80%) and 20 (20%) listings for training and test sets, respectively.  First, we built a model on the training data, and then we test its performance on the test set.

Typically, we are not interested in how well the method works on the training data. Instead, our goal is to assess the predictive accuracy we get when applying our method to previously unseen test data. In other words, we want to test the model's generalizability.
Normally, the test set is a smaller dataset than the training set, which the model did not see previously.  Moreover, The data splitting has to be unbiased. In particular, we have to randomly sample the data to guarantee that the testing and training sets are similar in terms of variation and representative.

<!--Talk about scikit learn train_test_split function-->



## Results



### Best Performance Model

A summary of the results is reported in Table ..



#### Linear Regression

As expected in \ref{sec:linear-regression}, incorporating such a large number of features (309) makes the linear regression model overfit the data. As shown in Table ~\ref{tab:results}, while training MSE of the linear regression model is quite good, the model performs poorly on the test set both in terms of   in terms of $MSE$ and $R^2$

#### Ridge Regression

By performing k-fold cross-validation with ten folds, we can find the tuning parameter's value that results in the smallest cross-validation error is 115. The test's MSE is associated with this value of  is 0.138.  The result represents a considerable improvement of ridge regression over the test MSE we got using least square regression.



#### Lasso Regression

Using cross-validation as described in \ref{ssec:cross-validation}, we find the optimized penalty value $\lambda$is 0.005. The associated test MSE is 0.1441, which is slightly higher than the test set MSE of the ridge regression.
Recall from that the advantage of using lasso regression over ridge regression is that lasso performs feature selection.

Lasso picked 153 variables while eliminated the other 125 features.

Figure ... shows the top 20 important features


It is not surprising that the two most important positive features are whether the type of listing is entire home, how many people the property accommodates, as theses are the main things customer would use  to search for properties in the first place.

Spatial features related to location are in the top 10.  Being in Hell's Hell's Kitchen,
Midtown, East Village, Chelsea, West Village, Upper West Side, Williamsburg,
Upper East Side, SoHo, Lower East Side is associated with an increase in the listing price.





#### Xgboost
As shown by the Table ~\ref{tab:results} XGboost consistently outperform these competing approaches in both mean squared error and R-squared. 

With this model, the features explain approximately 73% of the variance in the target variable and has a smaller than other regression model.



Apart from its superior performance, a benefit of using ensembles of decision tree methods like gradient boosting is that they can automatically provide estimates of feature importance from a trained predictive model. 





However, the training MSE and test MSE are quite different. Therefore the model could be improved even further with hyperparameter tuning.

