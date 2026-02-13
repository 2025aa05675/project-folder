# a. The problem statement

Credit card payment defaults pose serious risks to financial institutions. To reduce financial losses and enhance credit risk management tactics, it is essential to identify clients who are most likely to miss their next month's payment.

Building a machine learning classification model that can forecast whether a credit card customer will miss their payment in the upcoming month is the aim of this project.

The model uses past customer information, such as demographics, credit limits, repayment records, bill amounts, and past payments, to categorize clients into:

0 = No Default
1 → Default

This project uses data-driven insights to assist financial institutions in:
->Boost methods for risk assessment
->Cut down on bad debt
->Make the best choices for credit approval
->Increase the general stability of finances

# b. Dataset Description

This dataset contains information about credit card clients, including their demographic factors, credit data, payment history, bill statements, and default payment status.

It consists of 25 variables, which are categorized as follows:
| Variable      | Description                                                                                         |
| ------------- | --------------------------------------------------------------------------------------------------- |
| **ID**        | Unique ID of each client                                                                            |
| **LIMIT_BAL** | Amount of given credit in NT dollars (includes individual and family/supplementary credit)          |
| **SEX**       | Gender (1 = Male, 2 = Female)                                                                       |
| **EDUCATION** | Education level (1 = Graduate School, 2 = University, 3 = High School, 4 = Others, 5 & 6 = Unknown) |
| **MARRIAGE**  | Marital status (1 = Married, 2 = Single, 3 = Others)                                                |
| **AGE**       | Age in years                                                                                        |

Repayment Status (April–September 2005)
These variables indicate past repayment behavior.
Values range from:
-1 → Pay duly
1 to 9 → Payment delay (number of months delayed)

| Variable | Month          |
| -------- | -------------- |
| PAY_0    | September 2005 |
| PAY_2    | August 2005    |
| PAY_3    | July 2005      |
| PAY_4    | June 2005      |
| PAY_5    | May 2005       |
| PAY_6    | April 2005     |

Bill Statement Amounts (NT Dollars)
These represent the monthly bill amounts for the last six months.

| Variable  | Month          |
| --------- | -------------- |
| BILL_AMT1 | September 2005 |
| BILL_AMT2 | August 2005    |
| BILL_AMT3 | July 2005      |
| BILL_AMT4 | June 2005      |
| BILL_AMT5 | May 2005       |
| BILL_AMT6 | April 2005     |

Previous Payment Amounts (NT Dollars)
These variables indicate how much the client paid in the previous six months.

| Variable | Month          |
| -------- | -------------- |
| PAY_AMT1 | September 2005 |
| PAY_AMT2 | August 2005    |
| PAY_AMT3 | July 2005      |
| PAY_AMT4 | June 2005      |
| PAY_AMT5 | May 2005       |
| PAY_AMT6 | April 2005     |

Target Variable

| Variable                       | Description                       |
| ------------------------------ | --------------------------------- |
| **default.payment.next.month** | Default payment (1 = Yes, 0 = No) |


# c. Models used
## Model Performance Comparison

| ML Model                    | Accuracy | AUC  | Precision | Recall | F1 Score | MCC  |
|----------------------------|----------|------|-----------|--------|----------|------|
| Logistic Regression        | 0.58     | 0.65 | 0.62      | 0.45   | 0.52     | 0.17 |
| Decision Tree              | 0.69     | 0.74 | 0.76      | 0.56   | 0.64     | 0.40 |
| k-Nearest Neighbors (kNN)  | 0.58     | 0.61 | 0.57      | 0.59   | 0.58     | 0.15 |
| Naive Bayes                | 0.57     | 0.66 | 0.54      | 0.90   | 0.68     | 0.18 |
| Random Forest (Ensemble)   | 0.70     | 0.75 | 0.72      | 0.64   | 0.68     | 0.40 |
| XGBoost (Ensemble)         | 0.67     | 0.73 | 0.68      | 0.65   | 0.66     | 0.34 |

## Observations

## 📌 Model Performance Observations

| ML Model                     | Observation about Model Performance |
|------------------------------|-------------------------------------|
| Logistic Regression          | Achieved moderate performance. It showed reasonable precision but lower recall, indicating difficulty in identifying all default cases effectively. Suitable as a baseline model. |
| Decision Tree                | Performed better than Logistic Regression with improved accuracy and balanced precision-recall. Demonstrated good interpretability and handled nonlinear relationships effectively. |
| k-Nearest Neighbors (kNN)    | Showed average performance with balanced precision and recall but lacked strong predictive power compared to ensemble models. Sensitive to data scaling and parameter tuning. |
| Naive Bayes                  | Achieved very high recall, meaning it successfully identified most default cases. However, lower precision indicates higher false positives. Useful when minimizing missed defaults is critical. |
| Random Forest (Ensemble)     | One of the best-performing models. Delivered strong accuracy, balanced precision-recall, and high MCC. Reduced overfitting by combining multiple decision trees. |
| XGBoost (Ensemble)           | Demonstrated strong overall performance with good balance across all evaluation metrics. Efficient and robust, making it a competitive ensemble method for credit risk prediction. |
