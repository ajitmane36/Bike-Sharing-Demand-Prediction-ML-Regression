# Bike-Sharing-Demand-Prediction-ML-Regression.......
This project aims to build a predictive model that could predict the number of rental bikes required for each hour using the Seoul Bike Sharing dataset. Linear regression, Lasso (L1), Ridge (L2), ElasticNet, Decision Tree, Random Forest, and XGBoost algorithms are used to build a model to predict the number of rental bikes required for each hour.

#### <ins>Problem Statement</ins>
     Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is 
     important to make the rental bike available and accessible to the public at the right time as it lessens the
     waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern.
     The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.
#### <ins>Dataset</ins>
     The dataset contains weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, 
     Snowfall, Rainfall, the number of bikes rented per hour and date information.
     
     Attribute Information:
     Date : year-month-day
     Rented Bike count - Count of bikes rented at each hour.
     Hour - Hour of the day
     Temperature-Temperature in Celsius
     Humidity - %
     Windspeed - m/s
     Visibility - 10m
     Dew point temperature - Celsius
     Solar radiation - MJ/m2
     Rainfall - mm
     Snowfall - cm
     Seasons - Winter, Spring, Summer, Autumn
     Holiday - Holiday/No holiday
     Functional Day - NoFunc(Non Functional Hours), Fun(Functional hours)
#### <ins>Data Cleaning and Data Preprocessing</ins>
     [1] Handling Duplicate Values
     - Dataset having 0 duplicated values.
     [2] Handling Null / Missing Values
     - Dataset having 0 null values.
     [3] Removing Outliers
     - Interquartile Range in the skew symmetric curve used to remove outliers found in the Rented Bike Count, Wind speed (m/s) and Solar Radiation (MJ/m2) variables.
     [3] Data Wrangling and Feature Engineering
     - The variables day, month, and year were created from the variable Date, and the original variables deleted.
     - Datatype of the variable Date was transformed from object datatype to datetime64.
     [4] Confirming Presumptions
     - Using log and square root transformation, the distribution of the features Rented Bike Count, Wind speed (m/s), Solar Radiation (MJ/m2), Visibility (10 m), Rainfall (mm), and Snowfall (cm) was returned to normal.
     - All numerical variables are correlated with the dependent variable Rented Bike Count, but Solar Radiation (MJ/m2), Dew Point Temperature (°C) and Temperature (°C) are highly correlated with the dependent variable, which is good for a linear machine learning model.
     - From above, variables 'year','Dew point temperature(°C)', and 'Humidity(%)' have a high variance inflation factor, so we can remove them to reduce VIF
     [5] Features encoding
     - Label encoding used to encoding variables Seasons, Holiday, and Functional Day.
     [6] Data Scaling
     - MinMaxScaler preserves the shape of the original distribution. It doesn't meaningfully change the information embedded in the original data. So we used MinMaxScaler for scaling the dataset.
#### <ins>Exploratory Data Analysis</ins>
     These following graphs and plots were primarily created using Matplotlib and the Seaborn package.
     - Bar plot
     - Line plot
     - Box plot
     - Heatmap

     Performed EDA and reached the following conclusions:
     - Customers who travel most commonly use rented bikes in the morning at 8 A.M. and in the evening at 6 P.M.
     - When the humidity level is between 10% and 18%, people prefer to rent bikes.
     - When wind speed is between 2 m/s and 3.5 m/s, people consistently use rented bikes, and it is at its peak when wind speed is normal, which is 3.2 m/s.
     - Renting a bike is the best option for customers in dew point temperatures ranging from 12°C to 18°C. The use of a rented bike increases with increasing dew point temperatures, but it still reaches normal dew point temperatures.
     - According to the graph, solar radiation has no effect on customer use of rented bikes.
     - When it's not raining, people prefer rental bikes the most.
     - When there is no snowfall, most people opt to rent bikes. However, the majority of customers prefer to rent bikes when it snows up to 4 cm.
     - In the first 10 days of the month, most rented bikes are used by customers. Customers consistently use rented bikes in the last 15 days of the month.
     - In June, most rented bikes are used through the year, followed by October. Customers' use of rent bikes is at its peak from April to September.
#### <ins>Model Building</ins>
     We implemented the following machine learning models:
     - Linear Regression
     - Lasso (L1) Regression
     - Ridge (L2) Regression 
     - ElasticNet Regression 
     - Decision Tree 
     - Random Forest
     - XGBoost 
#### <ins>Models Evaluation</ins>
     - We used the R-squared score, Root Mean Squared Error, and the Mean of Residuals for the evaluation of each model.
#### <ins>Model Explainability</ins>
     - A higher feature importance score for features : Functioning Days, Rainfall (mm), and Seasons, respectively, indicates that those specific features have a larger influence on the model used to forecast a certain variable, respectively.
     - High values from the Hour, Temperature (°C), Solar Radiation (MJ/m2), and Functioning Day features have a positive impact on the model, while low values have a negative impact.
     - High values of the variables for Wind speed (m/s), Holidays, Snowfall (cm), Visibility (10m), Seasons, and Rainfall (mm) have a negative impact on the model, while low values have a positive impact.
#### <ins>Conclusion</ins>
     - The XGBoost regression model has the highest R-squared score, the lowest Root Mean Squared Error (RMSE), and has very close to having zero mean of residuals. Achieved high R-squared score of 0.90% using XGBoost.
     - As a result of the model's high accuracy, low error, and zero mean of residuals, the XGBoost regression model is the ideal and well-trained model for forecasting the number of rented bikes required per hour.
