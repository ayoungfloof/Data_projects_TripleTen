## Customer Churn Forecasting for Interconnect Telecom

**Description**

Interconnect, a telecom operator, seeks to proactively identify customers at risk of churning to reduce attrition and improve customer retention. By analyzing customer demographics, service usage, and contractual data, the aim is to build a machine learning model that predicts churn, enabling timely intervention with promotions and support.

**Objective**
- Merge and clean multiple datasets containing customer information.
- Conduct exploratory data analysis (EDA) to uncover patterns associated with churn.
- Engineer relevant features and preprocess the data for modeling.
- Train classification models to predict churn using AUC-ROC as the primary evaluation metric.
- Optimize the model and evaluate its accuracy to meet the sprint scoring criteria.

**Data Sources**
- The project uses four CSV datasets located in /datasets/final_provider/:
    - contract.csv: Customer contract details.
    - personal.csv: Demographics and account information.
    - internet.csv: Internet service subscriptions.
    - phone.csv: Phone service details.
    - Each dataset includes a customerID field used for merging.

**Approach**
- Data Preparation: Load and merge all datasets, check for duplicates and missing values.
- EDA: Explore churn distribution, customer demographics, service patterns, and correlations.
- Model Development: Train classification models including Logistic Regression, Random Forest, Gradient Boosting, KNN, SCM, and Stoacking.
- Evaluation: Measure model performance with AUC-ROC and Accuracy.
- Deployment Readiness: Select the most reliable model and summarize findings for stakeholders.

**Tools & Libraries**
- import pandas as pd
- import numpy as np
- import matplotlib.pyplot as plt
- import seaborn as sns
- from sklearn.model_selection import train_test_split
- from sklearn.preprocessing import StandardScaler
- from sklearn.ensemble import RandomForestClassifier
- from sklearn.linear_model import LogisticRegression
- from sklearn.ensemble import GradientBoostingClassifier, StackingClassifier
- from sklearn.neighbors import KNeighborsClassifier
- from sklearn.svm import SVC
- from sklearn.metrics import roc_auc_score, accuracy_score, classification_report
- from sklearn.model_selection import GridSearchCV
- import warnings
- warnings.filterwarnings("ignore")


## Overall Conclusion

This project aimed to build a reliable machine learning model to help Interconnect Telecom identify customers likely to churn. By predicting churn risk, the company can proactively offer incentives to retain valuable clients and reduce customer turnover.

**Key Accomplishments:**
- Data Integration & Preparation: We merged four datasets containing contract, personal, internet, and phone service information for 7,043 customers. We cleaned missing values, engineered a binary target variable (churn), and one-hot encoded categorical features for modeling.
- Exploratory Data Analysis: Analysis revealed that ~26.5% of customers churned. Service types, contract length, and payment methods appeared to have potential influence on churn behavior.
- Model Development: Several models were tested and evaluated using AUC-ROC and Accuracy:
    - Logistic Regression: AUC-ROC = 0.826, Accuracy = 78.8%
    - Random Forest: AUC-ROC = 0.822, Accuracy = 79.4%
    - Gradient Boosting: AUC-ROC = 0.841, Accuracy = 79.6%
    - KNN, SVM, Stacking were also tested, but Gradient Boosting showed the strongest performance.
- Model Optimization: Gradient Boosting was further tuned using GridSearchCV. The final tuned model achieved:
    - AUC-ROC = 0.8463
    - Accuracy = 80.7%

These metrics meet the project’s success threshold of AUC-ROC ≥ 0.81 and suggest the model is effective at identifying high-risk churners.

**Final Recommendation:**

The tuned Gradient Boosting Classifier is the best candidate for deployment. It offers strong predictive power and generalization, and can be integrated into the company’s CRM or retention workflow to prioritize customer outreach. Future improvements may involve retraining on more recent data, adding customer interaction history, or testing deep learning approaches for further gains.
