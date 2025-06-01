## Customer Churn Prediction for Beta Bank

**Overview**

Beta Bank is experiencing customer churn as clients gradually leave the service. This project aims to develop a machine learning model that predicts which customers are at risk of churning. Accurate predictions will help the bank proactively retain high-risk customers and improve overall customer engagement.

**Project Objective**
- Build a binary classification model to predict whether a customer will churn (leave the bank)
- Achieve a minimum F1 score of 0.59 on the test set
- Compare multiple models using both F1 and AUC-ROC metrics
- Address class imbalance to improve prediction quality
- Identify key factors that influence customer churn

**Data Sources**
- Dataset Path: Churn.csv
- The dataset contains historical customer data with the following features:
    - RowNumber: Index of the row
    - CustomerId: Unique customer ID
    - Surname: Last name
    - CreditScore: Creditworthiness indicator
    - Geography: Country of residence
    - Gender: Customer’s gender
    - Age: Age of the customer
    - Tenure: Number of years with the bank
    - Balance: Account balance
    - NumOfProducts: Number of banking products held
    - HasCrCard: Has credit card (1/0)
    - IsActiveMember: Customer activity status
    - EstimatedSalary: Estimated yearly income
    - Exited: Target variable — whether the customer left (1) or stayed (0)

**Tools & Technologies**
- Languages: Python (pandas, NumPy, scikit-learn)
- Visualization: matplotlib, seaborn
- Modeling: Decision Tree, Logistic Regression, Random Forest
- Evaluation: F1 Score, AUC-ROC, Accuracy, Confusion Matrix
- Tuning: Class Weighting, Manual Hyperparameter Tuning

**Methodology**
1. Data Preparation
- Loaded and explored dataset for class distribution and feature types
- Handled missing values and irrelevant features
- Encoded categorical variables and scaled numerical values
- Addressed class imbalance using class_weight, upsampling, and downsampling techniques
- Split the data into training, validation, and test sets
2. Model Training
- Trained three main classifiers:
- Decision Tree
- Logistic Regression
- Random Forest
- Performed manual hyperparameter tuning for each model
- Evaluated models using validation F1 scores and AUC-ROC
3. Evaluation Metrics
- F1 Score: Primary performance metric
- AUC-ROC: Evaluated model’s ability to distinguish churners from non-churners
- Confusion Matrix: Visualized classification quality on minority class

**Results & Comparison**
Final Model Performance
- Model |	F1 Score (Test) |	AUC-ROC:
    - Logistic Regression -	0.4970 -	—
    - Decision Tree -	0.5163 -	—
    - Random Forest -	0.6283 -	0.8596
- Random Forest was the top-performing model on both F1 score and AUC-ROC

**Feature Importance (Random Forest)**
- Feature |	Influence:
    - Balance -	High
    - Age -	High
    - NumOfProducts -	Medium
    - IsActiveMember -	Medium
    - CreditScore -	Low
    - Geography -	Low

**Sanity Check**
- Customers with high credit scores, low balances, and active usage had low churn risk
- Inactive customers with high balances and low product engagement were flagged at risk
- Model behaved logically on custom edge cases

**Final Verdict**
- Best Accuracy:	Random Forest
- Easiest to Interpret:	Decision Tree
- Weakest Performance:	Logistic Regression
- Deploy the Random Forest model for highest performance
- Decision Tree could serve as a fallback if interpretability or speed is prioritized

**Recommendations**
- Customer Retention Focus: Target inactive customers with high balances for retention strategies
- Cross-sell Opportunities: Encourage broader product adoption to reduce churn likelihood
- Risk Monitoring: Monitor customers with low credit scores and inactivity

**Conclusion**

This project successfully built a customer churn prediction model that meets the performance threshold (F1 ≥ 0.59). The Random Forest model stood out with an F1 score of 0.6283 and AUC-ROC of 0.8596, making it the best choice for deployment at Beta Bank. The bank can now use this model to proactively address churn risk and enhance customer loyalty.
