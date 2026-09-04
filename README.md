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
| Logistic regression | Linearity in the log-odds, multicollinearity | Correlation and VIF checks showed multicollinearity among some predictors, which was addressed before fitting the model | Linearity in the log-odds was not directly tested, so coefficient interpretations should be treated with caution |
| GAM | Smooth, continuous relationship between tenure and churn, chosen inputs are reasonably additive | Logistic and LOWESS plot for churn vs. tenure was compared, substantial deviation found | The chosen features might interact with each other, and that would not be captured in the splines |

## Model Comparison

| Model | Performance Evidence | Interpretability Strength | Interpretability Weakness |
|---|---|---|---|
| Linear regression | Linear Accuracy = 0.7868, ROC-AUC = 0.8129 | Coefficients show changes in predicted churn probability | Not designed for binary outcomes and can produce invalid probabilities|
| Logistic regression | Accuracy = 0.8038, ROC-AUC = 0.8333 | Coefficients can show how each feature is associated with higher or lower odds of churn | Coefficients assume a linear relationship with the log-odds and do not naturally capture nonlinear effects |
| GAM | GAM Accuracy: 0.7871, GAM ROC-AUC: 0.8368 | We chose a combination of categorical and smooth features, the non-linear relationship with tenure can be easily visualized now | The smooth curve for tenure is less concise and harder to interpret easily, and it may be affected by noise or overfitting as well |

## Recommendation

Recommended model:
Logistic Regression

Why this model:
Logistic regression seems like the best choice because it performs well and is still easy to interpret. Its ROC-AUC is comparable to GAM, though accuracy is higher and the coefficients are more straightforward to explain.

What the company can responsibly conclude:
The company can use the model to see which customer features are related to higher or lower churn risk. In looking at any 1 feature in this analysis, however, it would be assuming all others held constant.

What the company should not conclude yet:
The company should not assume that these features directly cause churn. The model only shows relationships in the current data.

One next analysis we would run:
We would test the model on new customer data to see if the results and patterns stay consistent. We could also perform causal analysis between carefully chosen features and churn to come up with a deeper understanding of what causes churn.


## AI Disclaimer

GenAI tools like ChatGPT were used to help understand the core concepts involved in this assignment, as well as to write portions of the code used herein. 