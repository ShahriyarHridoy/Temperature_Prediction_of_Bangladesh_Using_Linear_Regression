
# Temperature_Prediction_of_Bangladesh_Using_Linear_Regression

# Overview

### for datails see the link docs=> https://github.com/ShahriyarHridoy/Temperature_Prediction_of_Bangladesh_Using_Linear_Regression/blob/main/Group-6%20ML%20project%20Report%201037%2C%201039%2C%201040%2C%201044.docx

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

## Transformations

Log transformation of the CO2 emission data gave the best result of Global CO2 emission. 

Transformation attempt:
1.Log transformation
2.Square root transformation
3.Inverse transformation
4.Square-root inverse transformation

## Results and Discussion:

We have finally worked on 3 yearly features : GlobalCOemission, Solar radiation of
Bangladesh, Rainfall in Bangladesh. Prior to any transformation, our  the value was 0.607. We have computed various transformations on these features which we provided in detail in the previous section. Among them, log transformation on the feature “GlobalCOemission” has increased the  value from 0.607 to 0.619. Log transformation, square-root transformation, cube-root transformation, exponential transformation and inverse transformation on the other features did not increase the value, rather decrease it.

## Final Equation

y(TEMPERATURE) = 𝛃0 + 𝛃1*log(CO2_global) + 𝛃2(Solar_Radiation_BD) + 𝛃3(Rainfall_BD)

## Conclusion and Future Work

From this finding, we found that there is a relationship between CO2 emission of the world, rainfall and solar radiation with temperature. After performing linear regression, evaluating the p-value based on residuals less than 0.05 (significance level) rejects the null hypothesis which indicates impasse on the assumptions. We found the best possible R2 value to be 0.619, which is not very high but not too low. The value of R2 could be increased if we considered some other related features which are important factors of temperature change. Future work could also be - collecting more data of the considered features. For example, if we could collect monthly or even daily data of the following features, our results could have improved.
