# Plan Recommendation Model for Megaline Subscribers

## Description:
This project focuses on building a machine learning model to recommend updated plans for Megaline subscribers based on their usage patterns. The goal is to analyze customer behavior and create a classification model that predicts whether a user should switch to the "Smart" or "Ultra" plan.

## Objective:
Develop a machine learning model with the highest possible accuracy to classify subscribers into one of two plans.
Ensure the model meets or exceeds the required accuracy threshold of 0.75 on the test dataset.

## Data Source:
The dataset users_behavior.csv includes monthly usage behavior for each subscriber, such as:

calls: Number of calls made.
minutes: Total call duration in minutes.
messages: Number of text messages sent.
mb_used: Internet traffic used in megabytes.
is_ultra: Current plan (Ultra = 1, Smart = 0).

## Approach:
1. Data Preparation:
Load and inspect the dataset to understand its structure and content.
Split the dataset into training, validation, and test subsets.
2. Model Development:
Train various machine learning models with different hyperparameters.
Compare models based on validation accuracy to select the best-performing one.
3. Model Evaluation:
Evaluate the chosen model's performance on the test set.
Conduct a sanity check to ensure the model behaves logically and reliably.

## Tools:
Libraries: pandas, scikit-learn, and matplotlib.
Machine Learning Models: Decision Tree, Random Forest, Logistic Regression, and others as needed.

## Deliverables:
A trained classification model that meets the accuracy requirement.
Analysis of different models and their hyperparameters.
Insights and recommendations based on model performance.
This project will help Megaline improve customer satisfaction by identifying and recommending the most suitable plan for their subscribers based on their monthly usage behavior.

# Feature Importance Analysis
The Decision Tree model identifies the following features as most influential for predicting whether a subscriber should switch to the "Ultra" plan:

mb_used (Internet usage in MB):

Importance: 51.38%
Internet usage is the most significant factor influencing the prediction. Users with higher internet usage likely need the "Ultra" plan.
minutes (Total call duration in minutes):

Importance: 27.46%
The total time spent on calls also significantly contributes to the prediction. Higher call durations may indicate a preference for a more comprehensive plan like "Ultra."
messages (Number of text messages):

Importance: 19.36%
Text messaging usage is a moderately important factor. Users sending more messages may benefit from the "Ultra" plan.
calls (Number of calls):

Importance: 1.81%
The number of calls made is the least significant factor. While it provides some information, it doesn't heavily influence the prediction.


Feature Importance Analysis
The Decision Tree model identifies the following features as most influential for predicting whether a subscriber should switch to the "Ultra" plan:

mb_used (Internet usage in MB):

Importance: 51.38%
Internet usage is the most significant factor influencing the prediction. Users with higher internet usage likely need the "Ultra" plan.
minutes (Total call duration in minutes):

Importance: 27.46%
The total time spent on calls also significantly contributes to the prediction. Higher call durations may indicate a preference for a more comprehensive plan like "Ultra."
messages (Number of text messages):

Importance: 19.36%
Text messaging usage is a moderately important factor. Users sending more messages may benefit from the "Ultra" plan.
calls (Number of calls):

Importance: 1.81%
The number of calls made is the least significant factor. While it provides some information, it doesn't heavily influence the prediction.

# Conclusion: Key Insights
The model relies heavily on internet usage (mb_used) and call duration (minutes) for making decisions.
Text messages (messages) play a secondary role.
The number of calls (calls) has minimal impact, suggesting it may not vary significantly between the two plans or is not as indicative of plan suitability.
