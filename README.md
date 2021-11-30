## Problem Statement and Background

Property sale transactions have always been heavily reliant, both formally and informally, by the size of their total land area and the use of features such as the number of bedroom and bathrooms as a gauge to try to measure it. Our data science team from Kishan Analytics is proposing the use a of other housing features to build an regression accurate model for predicting home values in Ames.

This report details the use of a [*dataset*](http://jse.amstat.org/v19n3/decock.pdf) detailing the sale of individual residential properties in Ames, Iowa from 2006 to 2010 for the purpose of building our predictive model. The original dataset contains 2,930 observations and a large number of explanatory
variables (23 nominal, 23 ordinal, 14 discrete, and 20 continuous) involved in assessing home
values. Our aim is to identify other housing features that contribute significantly to sale prices so that real estate agents can make use of our analyses and prediction models to help their client secure the best price for their properties.

--

### Datasets
This project uses the Ames housing data available on Kaggle, which includes 81 features describing a wide range of characteristics of 2,929 homes in Ames, Iowa sold between 2006 and 2010.  Our model is trained on 2,051 houses sold prior to 2010 and will be tested on 878 houses.

* [`train.csv`](./datasets/train.csv): Data for Model Training
* [`test.csv`](./datasets/test.csv): Data for Model Testing

---

## Data Dictionary
Please refer to text documentation as included in De Cook's (2001) paper for data dictionary. [*Source*](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

---

##Analysis Summary
Based on Ridge Regression model coefficients, 'Neighborhood_GrnHill', 'Functional_Typ', 'Heating_GasW', 'Functional_Min2', 'BsmtCond_Po', 'SaleType_Oth have a more significant positive impact on the model while 'Foundation_Slab', 'Condition2_Artery', 'Neighborhood_Edwards', 'Functional_Maj2', 'Exterior1st_AsbShng', 'Neighborhood_MeadowV', 'GarageQual_Po', 'RoofStyle_Mansard', 'ExterCond_Po', 'MSZoning_A (agr)', 'Heating_Grav', 'HeatingQC_Po', 'Functional_Sal' have a more negative impact on the model.

---

## Conclusions and Recommendations

Our Ridge Regression model is an improvement from the baseline linear regression model, having a cross-valuation score of 0.89 as compared to 0.87, with a slight improvement in r-squared score from approximately 90%-94% to 91&-94% in explaining variance.
Based on the MSE, the model is performing similarly on both the testing set and training set, which means that it is likely not overfitting or underfitting the data. Based on the R^2, the model is explaining approximately 91-94% of the variance in the Y data.

Based on exploration of the Ames Housing data and analysis of the predictive model results, we can conclude that houses with the below features have a more significant positive impact on the sale price of houses:
	•	Located in the neighborhood of GreenHill
	•	Possess typical functionality or with slight function deduction
	•	Have hot water or steam heat
	•	Low basement height of less than 70inches
	•	Sale types other than warrently deed, home just contructed and sold, contract down pay moment, warranty deed and down payment, new homes constructed and court officer deed.

On the other hand, houses with the below features have a more significant negative impact on the sale price of houses:
	•	Possess salvage-only home functionality or with major function
	•	Have poor heating quality
	•	Have gravel heated
	•	Located in the agriculture mail service zoning
	•	Have poor exterior quality with zsbestos xhingles as well as Mansard roof style
	•	Have poor quality garage
	•	Located in the Meadow Village or Edwards neighborhood
	•	Located along adjacent to arterial street

Other than inputting the features of the house of interest into our predictive model and getting a Sale Price based on a more holistic evaluation of its Sale Price, real estate agents can focus on the more significant features and help client to straighten up their houses in hope of scoring a better sale price.

Future improvements to the model can include narrowing down to the important features for training the model and utilising K-Folds cross-validation for the regression. Any new data collected would be used to train the model at regular intervals to ensure that its predictions are up-to-date with the latest real estate trends.

