# Customer Churn Prediction for Beta Bank

### Project Description:
Beta Bank is facing customer churn as customers gradually leave the bank each month. To mitigate this issue, the bank wants to predict which customers are likely to leave. This project aims to build a machine learning classification model that identifies customers at risk of churning, helping Beta Bank take proactive measures to retain them.

### Objective:
The primary goal is to build a machine learning model with an F1 score of at least 0.59. The model will classify whether a customer will leave (churn) or stay based on their past behavior. Additionally, the AUC-ROC metric will be evaluated for comparison with the F1 score.

### Data Source:
The data file is Churn.csv, containing historical customer data with the following features:

RowNumber: Index of the data row.<br>
CustomerId: Unique customer identifier.<br>
Surname: Customer surname.<br>
CreditScore: Credit score of the customer.<br>
Geography: Country of residence.<br>
Gender: Gender of the customer.<br>
Age: Customer's age.<br>
Tenure: Duration of account tenure (in years).<br>
Balance: Customer's account balance.<br>
NumOfProducts: Number of banking products used.<br>
HasCrCard: Whether the customer has a credit card.<br>
IsActiveMember: Whether the customer is active.<br>
EstimatedSalary: Estimated annual salary.<br>

### Approach:
Data Preparation:

Load and inspect the dataset.
Preprocess features, ensuring categorical and numerical columns are appropriately handled.
Address class imbalance using techniques like class weighting, upsampling, and downsampling.
Model Development:

Split the data into training, validation, and test sets.
Train and evaluate several classification models:
Decision Tree Classifier
Logistic Regression
Random Forest Classifier
Tune hyperparameters to improve model performance.
Compare models based on F1 score and AUC-ROC metrics.
Model Evaluation:

Evaluate the final model using the test set.
Perform a sanity check to ensure model consistency.

### Tools Used

import pandas as pd                          
from sklearn.model_selection import train_test_split  
from sklearn.tree import DecisionTreeClassifier       
from sklearn.linear_model import LogisticRegression  
from sklearn.ensemble import RandomForestClassifier  
from sklearn.metrics import(  
    accuracy_score,                       
    f1_score, roc_auc_score,             
    confusion_matrix, ConfusionMatrixDisplay
)
### Deliverables:
A trained classification model that achieves the required accuracy and F1 score.
Comparative analysis of different models with tuned hyperparameters.
Insights into customer behavior and the key factors influencing churn.
Visualizations of model performance, including confusion matrices.

### Overall Insights from the Project
Data Balance and Class Imbalance<br>

The dataset had a significant class imbalance, where 80% of customers had not exited (0), and only 20% had exited (1).<br>
This imbalance was addressed using class weight adjustments, which allowed the models to give more importance to the minority class (exited customers) and improved performance.<br>

Model Performance<br>

Baseline Model: Without class imbalance adjustments, the initial decision tree achieved an F1 Score of 0.5177 and accuracy of 78.2%, indicating poor performance on the minority class.<br>
Decision Tree Model (Class Weight): Adjusting for class imbalance improved the F1 score slightly to 0.5163 with accuracy rising to 79.2%.<br>
Logistic Regression Model: Even with class weight adjustments, Logistic Regression struggled with complex patterns, yielding an F1 Score of 0.4970 and accuracy of 67.0%.<br>
Random Forest Model (Class Weight): This model outperformed all others. After hyperparameter tuning, the best Random Forest model achieved an F1 Score of 0.6532 on the validation set and 0.6283 on the test set, with AUC-ROC of 0.8596.
Key Insight: Random Forest emerged as the best model, balancing both precision and recall for predicting customer churn effectively.

Feature Importance<br>

From the Random Forest model's analysis:<br>
Balance (account balance) and Age were the most significant predictors of churn.<br>
Number of Products used, and whether the customer was an Active Member also played crucial roles.<br>
Credit Score and Geography contributed less to the prediction.<br>
Key Insight: Customers with higher balances and older ages showed varying churn probabilities. Active membership and product usage also influenced retention likelihood.<br>

Sanity Check Insights<br>

Edge cases demonstrated that the model behaved logically:<br>
Customers with high credit scores, zero balance, and high activity had low churn probabilities.<br>
Customers with low credit scores, inactivity, and high balance were flagged as moderate risk.<br>
The predictions aligned with expectations, highlighting the reliability of the trained Random Forest model.<br>

Business Impact and Recommendations<br>

Customer Retention Focus: Target customers with high account balances who are inactive or under-engaged, as these factors increase churn risk.<br>
Improve Engagement: Encourage customers to remain active and diversify their product usage (e.g., cross-sell products).<br>
Monitor High-Risk Segments: Specifically, customers with low credit scores and high balances need closer attention to prevent churn.<br>

Final Model Performance<br>

The Random Forest model achieved the highest F1 score on the test set (0.6283) and demonstrated robust performance with AUC-ROC of 0.8596.<br>
This performance meets the project's requirement of F1 ≥ 0.59.
