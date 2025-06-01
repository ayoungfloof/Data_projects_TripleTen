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

## Conclusion & Recommendations

This project successfully developed a machine learning pipeline to predict customer churn with high confidence. The tuned Gradient Boosting Classifier is the best candidate for deployment. It offers strong predictive power and generalization, and can be integrated into the company’s CRM or retention workflow to prioritize customer outreach. The final Gradient Boosting model achieved:
- AUC-ROC: 0.846
- Accuracy: 80.7% 
This model enables Interconnect Telecom to:
- Identify high-risk customers before they leave
- Automate CRM segmentation
- Support proactive retention offers

**Opportunities for Futrure Improvement:**
- Incorporate real-time customer activity logs (e.g., support tickets, usage spikes)
- Use recent customer data to ensure relevance
- Evaluate deep learning models or AutoML pipelines
- Integrate the model into a business dashboard with Streamlit
