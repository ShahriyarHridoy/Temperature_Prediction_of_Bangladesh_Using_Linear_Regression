
# Temperature_Prediction_of_Bangladesh_Using_Linear_Regression

As a result of global warming, there is a significant change in our climate. There are several reasons for global warming and as a result of global warming there are changes in different aspects of nature. In this finding, we considered CO2 emission as a potential reason for global warming, we considered solar radiation and rainfall as potential reasons for climate change and we considered temperature as a candidate of climate change indicator. In this case, the scope can be very large. So, we considered the temperature in Dhaka - which we wanted to predict. For  predicting the temperature (target variable) of Bangladesh from feature variables - Bangladesh CO2 emission, global CO2 emission, solar radiation and rainfall data of Bangladesh.
## Data Source

For this prediction, we did not collect data by ourselves. Therefore, we relied on secondary data sources. But all secondary sources are not reliable. So we relied on websites of the Bangladesh Government and International data source which is trusted and used by : Harvard, Stanford university; The Guardian, The New York Times, CNN, BBC and other news media.

Temperature and solar radiation dataset:
http://barcapps.gov.bd/climate/

CO2 emission dataset:
https://ourworldindata.org/co2-and-other-greenhouse-gas-emissions

Rainfall Data:
https://oasishub.co/dataset/bangladesh-historical-daily-rainfall-record-1948-2014-bangladesh-meteorological-department





## Methodology:

Data preprocessing:

We did not find a ready made dataset for our analysis. We had to merge some datasets from different sources to calculate our statistical analysis. We considered the following steps for our data pre-processing.

1.For rainfall data, we did not consider the following months - December, January, February, March - as there was little to no rain data in these months.
2.We extracted the solar radiation data and temperature data of Bangladesh from a large unstructured dataset. 
3.We had daily rainfall data, so we calculated the mean rainfall value for each month. 
4.For each month, we considered rainfall and temperature data and calculated the r-squared value. 

April:

May:


June:



July:


August:



September:


October:
	

November:
	



From this analysis report we found that, after comparing to other months we found that, there is a significant difference in R2 value on the month October. Therefore, for feature selection, we considered the rainfall and temperature value of the month October.

## Assumptions of Linear Regression

Here we are going to cover all six assumptions that we need to check when doing a linear regression.

### Check linear relationship among feature and target variables
As it is logical and crucial to check after all, if there aren’t linear relationships why should we  use a linear model as there are plenty of non-linear models. Basically, it shows the relationship between independent and dependent variables. 
Let’s go for a scatter plot which is simple and good enough for checking linearity among variables.

As we can see global CO2 emission has linear relations but among others there are no more linear relationships. 


### Normality of errors

### Histogram




### QQ Plot

Error means residual which is the difference between predicted and actual values. It should follow a normal distribution. Easy to test using histogram or QQ plot, although difficult to read but more precise to interpret.

### No heteroscedasticity (common variance)
Data should have homoscedastic means the residuals are equal across the regression line. While plotting residual vs fitted scaler plot, there shouldn’t be any pattern in error terms.


Now we know what this is, but to test whether heteroscedastic is present or not. We have to perform the Goldfeld Quandt Test.

Null hypothesis: Error terms are homoscedastic
Alternative hypothesis: Error terms are heteroscedastic

As a result of p-value and F- statistics from the test, if p-value is more than 0.05 then we can’t reject the null hypothesis that error terms are homoscedastic which is good.




### No autocorrelation
Error terms should not form any pattern and are independent. What autocorrelation means is that current value is dependent on historic values & definite unexplained patterns.

Now we are ensuring the absence of autocorrelation using the jungbox test.
Null hypothesis: Autocorrelation is absent
Alternative hypothesis: Autocorrelation is present

If p value is less than 0.05 we reject the null hypothesis that error terms are not autocorrelated. We got 0.1017, rejecting null hypothesis and accepting that autocorrelation is present.



As spikes outside the confidence interval confirms the signs of autocorrelation and seasonality factor.

### No multicollinearity
The extent to which multiple independent variables are correlated. It affects coefficient and p-values, but doesn’t influence the prediction. It clarifies the role of each independent variable and reduces severe multicollinearity. 







With variance inflation factor and confusion, we can view the importance of each variable.
## Selected Features:

Considering the collinearity relation, we considered not to use the CO2-bd feature. So, finally the featured we considered are:

1.CO2-world (CO2 emission of the world per year)
2.Solar Radiation (Solar Radiation of the world per year)
3.Rainfall (Rainfall data of October in Dhaka per year)
Target feature: Temperature (Temperature data of October in Dhaka per year)
## Transformations

Log transformation of the CO2 emission data gave the best result of Global CO2 emission. 

Transformation attempt:
1.Log transformation
2.Square root transformation
3.Inverse transformation
4.Square-root inverse transformation

Result without any transformation:


####  Log transformation on “CO2_world” feature:


####  Log transformation on “Solar_Radiation” feature:



####  Log transformation on “Rainfall” feature:



####  Exponential transformation on “Rainfall” feature:



####  Square-root transformation on “Rainfall” feature:



####  Cube-root transformation on “Rainfall” feature:



####  Inverse(1/x) transformation on “Rainfall” feature:



####  Inverse() transformation on “Rainfall” feature:



## Results and Discussion:

We have finally worked on 3 yearly features : GlobalCOemission, Solar radiation of
Bangladesh, Rainfall in Bangladesh. Prior to any transformation, our  the value was 0.607. We have computed various transformations on these features which we provided in detail in the previous section. Among them, log transformation on the feature “GlobalCOemission” has increased the  value from 0.607 to 0.619. Log transformation, square-root transformation, cube-root transformation, exponential transformation and inverse transformation on the other features did not increase the value, rather decrease it.

## Final Equation


y(TEMPERATURE) = 𝛃0 + 𝛃1*log(CO2_global) + 𝛃2(Solar_Radiation_BD) + 𝛃3(Rainfall_BD)




## Conclusion and Future Work

From this finding, we found that there is a relationship between CO2 emission of the world, rainfall and solar radiation with temperature. After performing linear regression, evaluating the p-value based on residuals less than 0.05 (significance level) rejects the null hypothesis which indicates impasse on the assumptions. We found the best possible R2 value to be 0.619, which is not very high but not too low. The value of R2 could be increased if we considered some other related features which are important factors of temperature change. Future work could also be - collecting more data of the considered features. For example, if we could collect monthly or even daily data of the following features, our results could have improved.