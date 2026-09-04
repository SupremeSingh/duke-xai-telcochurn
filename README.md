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
| GAM |  |  |  |

## Model Comparison

| Model | Performance Evidence | Interpretability Strength | Interpretability Weakness |
|---|---|---|---|
| Linear regression | MSE = 0.1490, R² = 0.2366 | Coefficients directly show changes in predicted churn probability | Can produce invalid probabilities; minimum prediction = -0.1131 |
| Logistic regression |  |  |  |
| GAM |  |  |  |

## Recommendation