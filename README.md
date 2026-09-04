# Team Name: TelcoChurn 

## Contributors 
- Manmit Singh 
- Xianyu Wang
- Lexie Lin 

## Dataset

Briefly describe the Telco Customer Churn dataset and the churn prediction task.

The Telco Customer Churn dataset contains information on 7043 customers, including customer demographics, services, contract information, tenure, and charges. The prediction task is to use these customer features to predict whether a customer will churn.

## Assumption Checks

| Model | Key Assumptions Checked | Evidence | Concern |
|---|---|---|---|
| Linear regression | Linearity, multicollinearity, binary outcome | Tenure-churn relationship and predictor correlation | Churn is binary, relationships may be nonlinear, and correlated predictors may make coefficients unstable |
| Logistic regression |  |  |  |
| GAM | Smooth/Non-linear relationship between at least 1 input feature and the output | Logistic and LOWESS plot for churn vs. tenure was compared, substantial deviation found | The chosen features might interact with each other, and that would not be captured in the splines |

## Model Comparison

| Model | Performance Evidence | Interpretability Strength | Interpretability Weakness |
|---|---|---|---|
| Linear regression | MSE = 0.1490, R² = 0.2366 | Coefficients directly show changes in predicted churn probability | Can produce invalid probabilities; minimum prediction = -0.1131 |
| Logistic regression |  |  |  |
| GAM | GAM Accuracy: 0.7885, GAM ROC-AUC: 0.8368 | We chose a combination of categorical and smooth features, the non-linear relationship with tenure can be easily visualized now | It might be hard to interpret or get granular detail from the spline for tenure other than the big-picture non-linearity |

## Recommendation


## AI Disclaimer

GenAI tools like ChatGPT were used to help understand the core concepts involved in this assignment, as well as to write portions of the code used herein. 