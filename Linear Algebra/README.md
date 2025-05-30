# Evaluating Machine Learning for Insurance Benefits Prediction

## Description
This project explores the potential of Machine Learning to improve customer analysis for the Sure Tomorrow Insurance Company. The company seeks to enhance its marketing strategies, predict insurance benefits, and protect client data while maintaining model performance. Using classification models, linear regression, and data obfuscation techniques, this project will evaluate how Machine Learning can assist in customer profiling and risk assessment.

## Objective
The goal of this project is to develop and test various Machine Learning models for the following tasks:

- Customer Similarity Analysis: Use k-Nearest Neighbors (kNN) to identify customers with similar characteristics, aiding targeted marketing efforts.
- Insurance Benefit Prediction: Build a classification model to determine whether a customer is likely to receive an insurance benefit and compare it to a dummy model.
- Predicting Insurance Benefit Count: Train a Linear Regression model to estimate the number of benefits a customer may receive.
- Data Obfuscation: Implement a secure data transformation that prevents unauthorized access to personal information without affecting model performance.

## Approach
- Data Preparation:
    - Load and inspect the dataset for missing values, outliers, and inconsistencies.
    - Perform scaling and transformation where necessary to ensure proper model performance.
- Model Development:
    - Train and evaluate a kNN classifier for customer similarity analysis.
    - Build a classification model to predict insurance benefits eligibility.
    - Develop a Linear Regression model to estimate the number of benefits received.
- Model Evaluation:
    - Use F1-score and confusion matrices to assess the classification model.
    - Use RMSE and R² scores to evaluate the Linear Regression model.
    - Compare model performance between scaled and unscaled datasets.
- Data Obfuscation & Security:
    - Transform the dataset using an invertible matrix to protect sensitive customer information.
    - Validate that obfuscation does not affect model performance by comparing RMSE and R² scores before and after transformation.
    
## Deliverables
- A trained classification model to predict insurance benefits eligibility.
- A Linear Regression model for estimating the number of benefits received.
- A data obfuscation algorithm that secures customer data without impacting model performance.
- A comparative analysis of model performance with original and obfuscated data.
- This project will help Sure Tomorrow Insurance assess the feasibility of Machine Learning for customer analysis while ensuring data security. The results will provide insights into how different models perform and whether data transformation techniques can be effectively used without compromising predictive accuracy.

## Conclusion: Findings

- Distance Metrics in kNN: The choice between Manhattan and Euclidean distance affects the way distances between points are calculated, influencing kNN classification results.
- Impact of Data Scaling: Scaling plays a critical role in kNN performance since it prevents large-valued features (e.g., income) from dominating distance calculations.
- Effect of k on F1 Score: Increasing k beyond 1 had no significant effect on the F1 score.
- Best kNN Performance: The highest F1 score (0.95) was achieved using scaled data with k = 1.
- Linear Regression Performance: Using the custom Linear Regression model, the model achieved an RMSE of 0.34 and an R² score of 0.66, indicating moderate predictive accuracy.
- Obfuscation and Model Consistency: Applying data obfuscation using an invertible transformation matrix had no effect on model performance. The Linear Regression model produced the same RMSE (0.34) and R² score (0.66), confirming that linear transformations preserve predictive capability.

## Summary
The analysis demonstrated that scaling improves kNN performance, while Linear Regression remains invariant to obfuscation. The findings highlight the importance of data preprocessing in kNN and the robustness of Linear Regression under linear transformations.
