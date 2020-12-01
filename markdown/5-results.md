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



##### Spatial Importance

Another important finding was the role of location features play in predicting price. In particular, location features located in Manhattan and Brooklyn borough are in the top 20 important variables to predict the price. In Manhattan and Brooklyn, tourists can find neighborhoods for almost any interest. Particularly, 

​	

- Sightseeing: Midtown is the heart of New York shopping and theater and home to some of its most iconic buildings.
- Nightlife:  More clubs are found in “Hell’s Kitchen,”
- Food: In Soho, tourists can experience a host of the highest-rated dining places.
- Theather: There is no more convenient home base than the Theater District,  located in 42nd Street to 50th Street west of Sixth Avenue. 
- For families: Upper West Side is bordered with parks and playgrounds and boasting both a children’s museum and the famed dinosaurs at the American Museum of Natural. This neighborhood is also considered one of the safest areas of New York City

neighbourhood Midtown 0.025008 Manhattan
neighbourhood Hell’s Kitchen 0.018545 Manhattan
neighbourhood East Village 0.015763 Manhattan
property type Other 0.015168
neighbourhood Bedford-Stuyvesant 0.014314 Brooklyn
neighbourhood West Village 0.014031 Manhattan
neighbourhood Chelsea 0.013612 Manhattan
neighbourhood Lower East Side 0.011874 Manhattan
neighbourhood Bushwick 0.011854 Brooklyn
neighbourhood Upper West Side 0.011682 Manhattan
neighbourhood Washington Heights 0.011659 Manhattan
neighbourhood SoHo 0.011582 Manhattan
room type Shared room 0.011304
neighbourhood Greenwich Village 0.010347 Manhattan
room type Hotel room 0.009697
neighbourhood Theater District 0.008575 Manhattan
neighbourhood Williamsburg 0.008490 Brooklyn
neighbourhood Crown Heights 0.007979 Brooklyn





```python
#Review the listings by boroname
plt.figure(figsize=(10,10))
sns.scatterplot(x='longitude', y='latitude', hue='boroname',s=20, data=data)
```





```python
#Plot the count by borough into a map
fig,ax = plt.subplots(1,1, figsize=(10,10))
bc_geo.plot(column='id', cmap='viridis_r', alpha=.5, ax=ax, legend=True)
bc_geo.apply(lambda x: ax.annotate(s=x.boroname, color='black', xy=x.geometry.centroid.coords[0],ha='center'), axis=1)
plt.title("Number of Airbnb Listings by NYC Borough")
plt.axis('off')
```



![image-20201016110023827](/Users/macbook/Library/Application Support/typora-user-images/image-20201016110023827.png)