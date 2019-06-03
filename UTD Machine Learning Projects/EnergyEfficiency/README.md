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


                            OLS Regression Results                            
==============================================================================
Dep. Variable:                     Y2   R-squared:                       0.888
Model:                            OLS   Adj. R-squared:                  0.887
Method:                 Least Squares   F-statistic:                     859.1
Date:                Wed, 25 Apr 2018   Prob (F-statistic):               0.00
Time:                        17:52:51   Log-Likelihood:                -1979.3
No. Observations:                 768   AIC:                             3975.
Df Residuals:                     760   BIC:                             4012.
Df Model:                           7                                         
Covariance Type:            nonrobust                                         
==============================================================================
                 coef    std err          t      P>|t|      [0.025      0.975]
------------------------------------------------------------------------------
const         97.2457     20.765      4.683      0.000      56.483     138.009
X1           -70.7877     11.225     -6.306      0.000     -92.824     -48.751
X2            -0.0661      0.015     -4.519      0.000      -0.095      -0.037
X3             0.0225      0.004      5.365      0.000       0.014       0.031
X4            -0.0443      0.008     -5.404      0.000      -0.060      -0.028
X5             4.2838      0.369     11.618      0.000       3.560       5.008
X6             0.1215      0.103      1.176      0.240      -0.081       0.324
X7            14.7171      0.888     16.573      0.000      12.974      16.460
X8             0.0407      0.076      0.534      0.594      -0.109       0.190
==============================================================================
Omnibus:                      104.668   Durbin-Watson:                   1.094
Prob(Omnibus):                  0.000   Jarque-Bera (JB):              230.547
Skew:                           0.767   Prob(JB):                     8.65e-51
Kurtosis:                       5.203   Cond. No.                     2.85e+16
==============================================================================

Warnings:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
[2] The smallest eigenvalue is 5.61e-25. This might indicate that there are
strong multicollinearity problems or that the design matrix is singular.


![Filtering Data](https://github.com/ahl160730/Data-Science-in-Python/blob/master/UTD%20Machine%20Learning%20Projects/PredictingBitcoinFeb2018/pictures/LoadClassification.PNG)

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