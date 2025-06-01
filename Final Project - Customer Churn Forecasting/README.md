## Customer Churn Forecasting for Interconnect Telecom

**Overview**

Interconnect Telecom aims to reduce customer attrition by proactively identifying users at high risk of churning. This project develops a machine learning solution to predict churn based on customer demographics, account information, internet and phone service details, and contract attributes.

By training and evaluating multiple classification models, the goal is to deliver a predictive tool that enables Interconnect’s retention team to prioritize outreach, offer incentives, and improve customer loyalty.

**Project Objective**
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

**Tools & Technologies**
- Languages: Python (pandas, NumPy, scikit-learn)
- Visualization: matplotlib, seaborn
- Modeling: Logistic Regression, Random Forest, Gradient Boosting, KNN, SVM, Stacking
- Evaluation: AUC-ROC, Accuracy
- Tuning: GridSearchCV

**Methodology**
1. Data Preparation
    - Merged all four datasets (7,043 rows) on customerID
    - Cleaned missing values and duplicates
    - Created a binary target variable based on EndDate (churned = 1)
    - Applied one-hot encoding to categorical variables
2. Exploratory Data Analysis
    - Churn rate: ~26.5% of users
    - Identified patterns by:
    - Contract type: month-to-month customers churned most
    - Payment method: electronic check correlated with higher churn
    - Service features: multiple service bundles linked to lower churn risk
3. Modeling & Evaluation
Tested multiple classifiers and measured their performance:
    - Model | AUC-ROC |	Accuracy:
        - Logistic Regression	0.826	78.8%
        - Random Forest	0.822	79.4%
        - Gradient Boosting	0.841	79.6%
        - Tuned GBM	0.846	80.7%
Other models tested: K-Nearest Neighbors, Support Vector Classifier, StackingClassifier
4. Model Tuning
Used GridSearchCV to optimize the Gradient Boosting Classifier. The final model meets the business goal of AUC-ROC ≥ 0.81.

**Methodology**





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
