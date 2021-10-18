# Executive Summary

We commenced the regression analysis by first getting an understanding of the data frame, selecting relevant variables and modifying columns in the wrong format. Before fitting the first model, the data was then subset into a training data set and a testing data set. The first model introduced the explanatory variables property type, review score, and number of reviews. The relevance of each variable on the 4-night log price was tested using the following criteria: 

Standard Error
The standard error provides an estimate of the difference from the coefficient estimate if we ran the model again. Ideally, this number should be small relative to the estimate, which appears to be the case in this model. 

t-value
In a regression model, the independent variables (in this case the number of reviews, review scores, and property type) should explain the dependent variable. For this, we require a correlation between the independent variable and each of the dependent variables. As the t-values in this model are all significantly different from 0, it can be assumed that all independent variables provide information to describe the independent variable. 

PR(|>t|)
This describes the probability of finding any value outside the confidence interval of t, hence we are looking for a small value. Since this is the case, all p values are highly significant, as also evidenced by the three stars depicted next to it)

To detect further explanatory variables, we proceeded to introduce additional variables, such as the room type to the model fitted. These variables also had a significant effect on the price, however, they also lowered some of the t-values of the already introduced variables, suggesting some multicollinearity.

In a second step, we fitted a new model, this time introducing beds, bedrooms, bathrooms, and space as the independent variables. Although all factors appeared to be significant in this model at first, introducing further explanatory variables and running a multicollinearity test (VIF) showed that bedrooms are highly correlated with some of the variables, which should not be surprising since the number of bedrooms tends to increase as the number of beds increases or as the Airbnb becomes larger. 

After getting a better understanding of some of the data, we decided to incorporate all explanatory variables in one model and run a multicollinearity test. All variables which appeared to be highly correlated, i.e. with a VIF score higher than 5, were excluded. This included bedrooms, as previously discussed, as well as maximum and minimum nights, host response time and rate, and availability. Running the model again excluding the highly correlated variables, we decided to exclude all variables with a \left|t\right|<2. 

The final model variables can be seen in the model11 section of the Rmd file. Although some variables, especially in the neighbourhood group, have high p-values, thus suggesting that they are not correlated with the dependent variable, this model overall appears to be well fitted, as evidenced by an R-squared score of 0.32, which is comparatively high to the other models we fitted. 
