## Plan Recommendation Model for Megaline Subscribers

**Overiew**

This project helps Megaline, a mobile telecommunications provider, optimize customer satisfaction and plan usage by recommending the most suitable mobile plan for each subscriber. Using monthly behavior data (calls, minutes, messages, and internet usage), the goal is to build a classification model that predicts whether a user should be on the "Smart" or "Ultra" plan.

**Project Objective**
- Analyze subscriber usage patterns from historical data
- Build and compare multiple classification models
- Select the best-performing model based on accuracy
- Meet the target accuracy of ≥ 0.75 on the test set
- Use feature importance to interpret model decisions and guide business recommendations

**Data Source**
The dataset users_behavior.csv includes monthly usage behavior for each subscriber, such as:
- calls: Number of calls made.
- minutes: Total call duration in minutes.
- messages: Number of text messages sent.
- mb_used: Internet traffic used in megabytes.
- is_ultra: Current plan (Ultra = 1, Smart = 0).

**Methodology**
1. Data Preparation
- Loaded and inspected the dataset
- Verified class distribution and checked for missing values
- Split data into training (60%), validation (20%), and test (20%) subsets
2. Model Training & Selection
- Trained and evaluated multiple classifiers:
- Decision Tree
- Random Forest
- Logistic Regression
- Compared validation accuracy to select the best-performing model
- Tuned hyperparameters (e.g., tree depth, number of estimators) for performance boost
3. Final Evaluation
- Best model selected based on validation results
- Evaluated on test set
- Accuracy goal of 0.75 was met
- Sanity check confirmed the model generalizes well

**Feature Importance (Decision Tree Model)**
- Feature |	Importance |	Insight
  - mb_used	51.38%	Primary driver of prediction — heavy internet users lean toward Ultra
  - minutes	27.46%	Longer call durations are associated with Ultra plan preference
  - messages	19.36%	Moderate influence; frequent texters more likely to benefit from Ultra
  - calls	1.81%	Least important; total number of calls doesn’t strongly influence plan suitability

**Conclusion**
- The model successfully met the required test set accuracy (≥ 0.75), making it viable for production use
- Key drivers of plan recommendation were internet usage and call duration
- Simpler usage metrics like total call count were found to have minimal predictive value

**Opportunities for Improvement**
- Introduce more granular time-based features (e.g., weekday vs. weekend usage)
- Segment the dataset by user demographics (if available) to improve targeting
- Explore ensemble techniques (e.g., voting classifiers) for performance boosting
- Develop a simple dashboard or API to deploy the model for use by customer service teams
