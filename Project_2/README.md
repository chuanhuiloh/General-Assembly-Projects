# Project 2: Identifying Features Influencing Value of Homes in Ames, Iowa

In this project, we wish to identify features of homes in Ames, Iowa which would strongly influence its value. These information would benefit homeowners who are looking to evaluate their current living environment while increasing their ability to negotiate for a higher price in a future sales. Homeseekers would also do well to note the particular presence or absence of certain features to make estimation of the price of the home they desire.

This analysis will be carried out by using a rich dataset of housing prices in Ames, Iowa to create a model for predicting sale price of a given home in the city. At the same time, the model chosen would quantify how the absence, presence and size of a particular feature affect the final selling price, enabling the homeowner to make cost benefit analysis on the type of enhancement in their homes.

---

## Executive Summary
For this project, I used the data from the Ames Housing Dataset. The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses. The following summarises the analysis process:

1. Impute or remove missing data on both the train and test datasets and review the outliers

2. Process the ordinal variables by applying a numeric rank based on notion of quality and reduce the cardinality of the features by grouping all categories with less than 20% of the total observations as 'Others'

3. Process the nominal variables by one-hot encoding. Remove continuous and ordical variables highly correlated with each other to reduce multicollinearity

4. Train and evaluate the performance of Standard Linear Regression, Ridge Regression, Lasso Regression and Elastic Net to arrive at the model

### Data Dictionary
Please refer to this [link](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt) for the variable description and categories.


### Key Conclusions and Recommendations

#### Conclusion

The submitted Lasso Regression with alpha = 92.43 model has a RMSE score of about \\$30,430 on Kaggle. The holdout RMSE is \\$28,636 for this model in comparison. This is in line with expectation, where the model do slightly worse on data it has not seen.

We may infer the influence of each features from the coefficient of this model. It is necessary to discuss the influence of features according to whether they are categorical or continuous in nature.

**Categorical Features**
1. The model show that houses which are of the categories MS SubClass 20, 40, 85 and 180 can command a premium of \\$5000 to \\$21000. These four classes are 1-STORY 1946 & NEWER ALL STYLES, 1-STORY W/FINISHED ATTIC ALL AGES, SPLIT FOYER and PUD - MULTILEVEL - INCL SPLIT LEV/FOYER respectively.

2. Houses with foundation made of poured concrete also commands higher prices of at least \\$9000

3. The presence of precast coverings lowers the sale price of a house by at least $5000

**Continuous Features**

1. Big open porches, total basement and ground living areas have a positive influence on house price, with price increase ranging from \\$3,000 to \\$9,000 per square foot.

2. Quite intuitively, quality related features such as overall finishing quality and height of basement are positive predictor of house price

3. A huge garage area negatively impacts the value of a house, decreasing by almost \\$7000 dollars for every square foot.

4. As expected, house price decreases with age and year since remod. 



### Recommendations and Further Study

1. Homeowners in Ames should consider expanding their own open porch to enhance their property value. The cost of building a porch is a 200-square-foot is between \\$4600 to \\$22000. [link](https://www.homeadvisor.com/cost/outdoor-living/build-a-porch/). The benefits clearly outweighs the cost.

2. Homeseekers would be advised to avoid houses with a huge a garage and and has precast coverings due to these features' drag on the property value.

3. While location is a known predictor of property price, the Lasso Regression model has penalised the coefficient of the `neigh_group` feature (whereby neighborhood were grouped into 5 groups according to house sale price) to zero, therefore eliminating its influence. More specific information on the exact addresses of the property instead of neighborhoods would be helpful to increase the predictive ability of the Lasso Regression model.

4. Most of the findings in this project are related to the features of the property itself, but it is known that economic conditions and interest rate are factors influencing property prices. The boxplot of `yr_sold` vs `saleprice` did not surface any significant change in distribution of the `saleprice` from 2006 to 2010 despite 2009 to 2010 being the years of the Global Financial Crisis. Perhaps, more data on the prevailing interest rates can be retrieved to see its correlation with housing price.