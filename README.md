# Statistical_Modelling_Price_Used_Vehicle

## Introduction
Owning a car is typically quite expensive, yet it is deemed a necessity by many households, especially in North America. In a 2021 study, 276 million vehicles were found to be registered with the US Department of Transportation. Additionally, 90% of US households have access to a vehicle and the average person was found to spend 100 minutes a day in a car (Borrelli, 2021). This highlights the significance of vehicles in our lives and the importance of selecting the correct vehicle.  

The used car market is of particular interest as, according to insights from McKinsey & Company, “the US used-car market is more than twice the size of the new-car segment and is outpacing it in growth” (Ellencweig et.al, 2019). The used car market in the United States may grow by close to 4 million units in the next 4 years (Yahoo!, August 2021). Additionally, purchasing a used car involves a more complicated decision making process than a new vehicle. As such, “used-car buyers spend about 40 percent more time researching online during the buying process than new-car buyers do” (Ellencweig et.al, 2019).  

There are many factors that will affect the cost of a car. In order to be conscientious consumers, we were interested in investigating the independent variables that can potentially influence the prices of cars. In this report, we investigate the various features from the “US Cars Data Set” (Alsenani, 2019) such as the vehicle registration year, state, brand, model, mileage, status (clean or used), etc.  

There are a number of commonly known factors that impact an individual’s decision when buying a used vehicle and affect the price. For example, a car with a clean title (no reported major accidents) will likely be worth more than one with salvage or rebuild status (has been in accident). Vehicles with higher mileage will have a lower resale price compared with vehicles with lower mileage (see the following figure). These assumptions were verified and quantified by conducting appropriate statistical tests.
Furthermore, we were interested to see if the price will be impacted by including interaction variables. For example, can both mileage and age of car together play a key role in the price prediction of a vehicle?  

All of these factors were considered using methodologies learned in DATA 603, including hypothesis testing, model diagnostics, ANOVA, etc. The results of these findings were used to find the best multiple linear regression model to predict the price of a vehicle in the United States.  

## Modeling Plan
We will use a series of methods to select the best model both conceptually and statistically. First, we will clean up the data set after doing some initial exploration. It is best practice to understand the data set and what each variable means. We will remove unrelated features based on our understanding of vehicle properties and reduce row records due to extremely low value counts. We will also use visualization methods to gain a better understanding of the data set. For example, using a scatter plot to reveal underlying trends between variables or using other visualization methods such as a boxplot or histogram to reveal the distribution of the data and detect outliers.  

To build our main effects model, we will start off with all the features in the linear regression model and find features that explain the most variance of the response variable. Given the many levels for all the qualitative features, we will avoid using auto selection programs like step-wise selection and elimination procedure. Instead, we will compare R2_adj and RMSE in different feature combinations. Variables that can explain a large portion of the response variance will be retained and those that only contribute a little will be discarded. The final main effects model will be confirmed by using individual t-tests for quantitative features and partial F-tests for qualitative features.  

Once the main effects model is confirmed, we will use selection programs like step-wise selection and elimination procedure to test for significant interaction terms. These results will be confirmed with individual t-tests. We will then identify higher-order terms by using a pairwise scatterplot and by conducting individual t-tests.  

After our final model is complete, we will use the following diagnostic tests to evaluate the model:  
- Linearity Assumption - Review the “Residuals vs. Fitted plot”
- Independence Assumption - Not applicable because the data set is not time series data
- Normality Assumption - Plot a histogram of the data, review the “Q-Q plot”, and use the Shapiro-Wilk normality test
- Equal Variance Assumption (heteroscedasticity) - Review the “Scale-Location plot” and use the Breusch-Pagan test
- Multicollinearity - Review ggpairs plot and variance inflation factors (VIF)
- Outliers - Review the “Residuals vs Leverage plot”, check Cook’s distance and leverage points
The model will be adjusted as needed if any of the assumptions above are violated. Once a final model is found, the coefficients will be interpreted. Lastly, with 20% of the data randomly retained for testing purpose, 80% will be used for the modeling training and the model will be used to predict car sale prices.
