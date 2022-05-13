# Appliance-Energy-Prediction
The Appliance Energy Prediction data provides temperature, pressure and relevant
weather data for every 10 min for about 4.5 months for a household. The objective is to
build a predictive model which could help in predicting the total appliance energy
consumption in the house proactively with the intention of offering some intuition in curbing
power consumption.


We try to understand the problem by performing Exploratory Data Analysis and use the
findings to engineer the features to improve the “learnability” of the dataset. In Feature
Engineering, we used the date feature and extracted components that could affect
consumption of energy in the household. These features include the hour of the day, the
phase of the day (morning, afternoon, evening, night) and day of the week. As time of the
day has a cyclic nature, we perform sine and cos transformations on hour of the day
feature. Interquartile method was used to handle numerical outliers in the dataset.
The attributes are rescaled using StandardScaler function from sklearn to have zero mean
and unit variance.This is done in order to bring down all the features to a common scale
without distorting the differences in the range of the values. This will ensure there is equal
contribution to the analysis.


After scaling and standardization, we spot-check and evaluate ten models based on their
RMSE, MAE, R-squared and adjusted R-squared values. Spot-checking is a way of
discovering which algorithms perform well on the machine learning problem. The models
deployed were: Linear Regression,Lasso Regression, Ridge Regression, Decision Tree
Regressor, Random Forest Regressor, Adaptive Boosting Regressor, Gradient Boosting
Regressor, Bagging Regressor, K Neighbors , Regressor and Linear SVM.
The linear models have assigned near zero weights to the random variable, negating its
influence in prediction of the target variable

Among deployed models, Random Forest Regressor had the highest R-squared score and
the lowest RMSE and MAE. These results were further improved using hyper parameter
tuning, producing a final R-squared score of 0.771. 

Using LIME and ELI5, we found that
this model’s predictions are mainly contributed by the time of the day and temperature in
rooms 3 and 2.
