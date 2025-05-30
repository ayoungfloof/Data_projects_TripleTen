# Optimizing Gold Recovery Process for Efficient Mining Operations

### Project Overview

This project focuses on analyzing and optimizing the gold recovery process for a mining operation. The goal is to develop a predictive model that evaluates and enhances the efficiency of gold recovery at different stages of the process, including flotation and purification. By analyzing the concentrations of metals (gold, silver, lead) and other parameters at various stages, the project aims to build a model capable of predicting the efficiency of the gold recovery process, ensuring data-driven decisions that maximize operational performance.

### Objective

- Data Preparation:
    - Open and inspect the datasets to understand their structure and contents.
    - Validate recovery calculation accuracy for the rougher stage.
    - Analyze and handle missing features in the test set.
    - Preprocess the data for further modeling steps.
    
- Data Analysis:
    - Investigate how metal concentrations change throughout the stages of purification.
    - Compare feed particle size distributions between training and test sets to ensure consistency.
    - Identify and handle anomalies in the total concentrations of substances at different stages.
    
- Model Development:
    - Develop a custom evaluation metric, symmetric Mean Absolute Percentage Error (sMAPE), to measure model performance.
    - Train multiple models and select the one with the best performance using cross-validation.
    - Test the selected model on the test set to evaluate its quality.
    
- Risk and Process Optimization:
    - Provide insights into the recovery process to improve the efficiency and stability of operations.
    
### Data Sources
The data provided comes from a mining operation and is structured into three datasets:
- Training Dataset: Contains historical data for model training.
- Test Dataset: Includes unseen data for evaluating model performance.
- Full Dataset: Combines training and test data for exploratory analysis.

### Technological Process
The project revolves around simulating and analyzing the stages of gold recovery:
- Flotation (Rougher Stage): Gold ore mixture undergoes primary processing to separate rougher concentrate and tails.
- Purification (Cleaner Stages): Rougher concentrate undergoes two stages of purification to produce final concentrate and new tails.

### Evaluation Metric
The project employs sMAPE (Symmetric Mean Absolute Percentage Error) as the key evaluation metric. This metric ensures that predictions are equally weighted, regardless of scale, to evaluate the performance of the recovery process at the rougher and final stages.

### Tools
- import pandas as pd
- import numpy as np
- from sklearn.metrics import mean_absolute_error
- import matplotlib.pyplot as plt
- import seaborn as sns
- from sklearn.ensemble import RandomForestRegressor
- from sklearn.linear_model import LinearRegression
- from sklearn.tree import DecisionTreeRegressor
- from sklearn.model_selection import train_test_split, cross_val_score, GridSearchCV, KFold, RandomizedSearchCV
- from sklearn.metrics import make_scorer
- import time
- from sklearn.dummy import DummyRegressor
- from sklearn.model_selection import RandomizedSearchCV
- from sklearn.preprocessing import StandardScaler
### Deliverables
-  trained and tested predictive model for recovery efficiency.
- Insights into metal behavior during the purification process.

-  Conclusion: Key Stages & Findings
 
1. Data Preprocessing & Feature Engineering

- The dataset contained features related to metal concentration, process parameters, and operational conditions across different recovery stages.
- Missing values were identified and handled appropriately to ensure data quality.
- The train and test datasets were properly aligned to maintain consistency in feature availability across different datasets.
- Feature engineering involved selecting relevant variables and dropping unnecessary columns (e.g., date columns) to enhance model performance.

2️. Exploratory Data Analysis & Insights

- Metal concentration changes over the recovery process:
    - The gold concentration increased from the raw feed to the final product, confirming that the purification process was effective.
    - Silver and lead concentrations decreased, aligning with expectations that unwanted metals are filtered out as processing continues.
- Distribution of recovery rates:
    - The Rougher Recovery stage had higher variability compared to the Final Recovery stage, making predictions for rougher recovery more challenging.
    - There were some anomalies in metal concentrations, which were investigated to ensure they did not distort model training.
- Relationship between process parameters and recovery:
    - Certain chemical reagents and feed rates had a measurable impact on recovery rates.
    - Understanding these relationships helps optimize process conditions to maximize gold yield.
    
3️. Model Training, Selection & Evaluation

- Three machine learning models were tested using cross-validation:
    - Decision Tree: sMAPE = -19.60
    - Linear Regression: sMAPE = -12.66
    - Random Forest: sMAPE = -12.06
- The Random Forest model was selected as the best-performing model based on its ability to capture complex, non-linear relationships in the dataset.

4. Model Tuning & Final Evaluation

- Random Forest was tuned to improve its generalization and predictive accuracy.
- The final model achieved the following performance on the test dataset:
    - Final Combined sMAPE: 10.67
- The final tuned Random Forest model improved overall performance compared to its untuned version that had a combined sMAPE of 12.06.

5. Model Validation & Sanity Checks

- A Dummy Regressor was used as a baseline, achieving a Final sMAPE of 10.35%
- This was an improvement from the original sMAPE for the random forest model was -12.06

6. Business Impact & Recommendations

- The Random Forest model successfully predicts recovery rates, providing valuable insights into factors affecting process efficiency.
- This model can be integrated into real-time monitoring systems to assist with process optimization and resource allocation in mining operations.

7. Final Takeaway:
- This project successfully demonstrated how machine learning can optimize gold recovery predictions, helping mining operations make data-driven decisions to maximize yield and efficiency. Further refinements, including advanced feature engineering and alternative modeling techniques, could further improve predictive accuracy
