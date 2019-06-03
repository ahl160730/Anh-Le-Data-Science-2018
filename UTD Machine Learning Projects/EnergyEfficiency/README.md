# Project 3: Energy Efficiency Prediction 
Code Author: Anh Hong  Le

#### Abstract:
- This study looked into assessing the heating load and cooling load requirements of buildings (that is, energy efficiency) as a function of building parameters.
- Source: The dataset was created by Angeliki Xifara and was processed by Athanasios Tsanas, Oxford Centre for Industrial and Applied Mathematics, University of Oxford, UK).

#### Assignment Goals: 

- Use neural network (Deep Learning) to predict the heating and cooling load of the building. 
- For this project you need to use some base Regression models and ensemble and compare r2_score. 
- Adding cooling load and heating load can define the overall load of the apartment. Study the trend of overall load and divide it into three classes, low efficient, high efficient and average efficient. Then train a deep learning model to predict the label. 



###  Table of Contents
- Data Exploration & Preprocessing
- Part I: Regression in Deep Learning - Heating & Cooling
- Part II: Base Regression & Ensemble Learning - Heating & Cooling
- Part III: Classification in Deep Learning - Overall Load
- SUMMARY

![featureselection](https://github.com/ahl160730/Data-Science-in-Python/blob/master/UTD%20Machine%20Learning%20Projects/EnergyEfficiency/pictures/FeatureSelection.PNG)

![Filtering Data](https://github.com/ahl160730/Data-Science-in-Python/blob/master/UTD%20Machine%20Learning%20Projects/EnergyEfficiency/pictures/LoadClassification.PNG)

## SUMMARY

### (1) Regression in Deep learning ( part I)

- After GridSearchCV for the best parameters, test scores are  0.94 in heating load and 0.92 in cooling load.
- Keras model has generalized well in both loads for the purpose of prediction.

### (2) Overall Performance in R-Squared ( part II)

##### Best Performer
- Random Forests demonstrates test scores of 0.9974 in heating load and 0.9729 in cooling load.

##### Medium Performer( runner-up)
- Decision Tree scores 0.9971 in heating load and 0.9723 in cooling load.

##### Low Performers
- Polynomial Lasso scores 0.7792 in heating load and 0.7798 in cooling load.

##### Bagging/ Boosting Ensemble
- Boosting improve the most out of used models as a whole. In contrast, Bagging messes up the scores from base regressors.
- Adaboost has improved R-squared of cooling load in KNN, Linear Ridge, Linear Lasso. Yet It messes up heating load.


### (3) Classification in Deep learning ( part III)

- Accuracy of test score is 95.83%. However, there is a small difference in using dummy variables to score 94.27%.
- From the frequency chart of classification, more than half of the building models are of medium efficiency ( more than 100).
- The rest of these instances are equally distributed between low and high groups of efficiency ( about 45 each).
