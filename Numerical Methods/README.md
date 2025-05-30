# Optimizing Used Car Price Predictions for Rusty Bargain
1. Description:
Rusty Bargain, a used car sales service, is developing an app to help customers quickly estimate the market value of their vehicles. By leveraging historical data, including technical specifications, trim versions, and pricing details, this project aims to build an accurate machine learning model to predict car prices. The primary focus is on achieving a balance between prediction quality, training efficiency, and inference speed to ensure a seamless user experience.

2. Objective:
    - Train multiple machine learning models to predict car prices based on historical data.
    - Compare different algorithms, including Linear Regression, Decision Tree, Random Forest, and Gradient Boosting models.
    - Evaluate model performance using the Root Mean Squared Error (RMSE) metric.
    - Optimize hyperparameters using Optuna to enhance model accuracy.
    - Assess the trade-offs between model accuracy and computational efficiency to determine the most suitable approach for deployment.

3. Data Sources:
- The dataset contains detailed information about used cars, stored in /datasets/car_data.csv, with the following key features:
    - Vehicle characteristics: VehicleType, RegistrationYear, Gearbox, Power, Mileage, FuelType, Brand, Model, NotRepaired
    - Listing details: DateCrawled, DateCreated, LastSeen, NumberOfPictures, PostalCode
    - Target variable: Price (in Euros)

4. Approach:
- Data Preparation:
    - Load and inspect the dataset for missing values and inconsistencies.
    - Perform feature engineering, including encoding categorical variables.
    - Handle duplicate or irrelevant features to improve model efficiency.

- Model Development:
    - Train and evaluate Linear Regression as a baseline model.
    - Implement Decision Tree, Random Forest, and LightGBM models.
    - Optimize hyperparameters using Optuna to improve performance.

- Performance Evaluation:
    - Measure model accuracy using RMSE to assess prediction quality.
    - Compare training time and inference speed across models.
    - Identify the best-performing model for deployment.

5. Tools & Libraries:
- Data Processing: pandas, numpy, sklearn.preprocessing
- Model Training: scikit-learn, lightgbm
- Hyperparameter Optimization: Optuna
- Visualization: matplotlib, seaborn, plotly

6. Deliverables:
- A trained machine learning model capable of accurately predicting used car prices.
- A comparative analysis of different models, highlighting their strengths and weaknesses.
- Insights into the impact of feature selection, hyperparameter tuning, and computational efficiency on model performance.
- Recommendations for further improvements, including potential enhancements like dimensionality reduction or alternative boosting methods (e.g., CatBoost, XGBoost).
- By the end of this project, Rusty Bargain will have a high-performing price prediction model that balances accuracy with efficiency, enabling a robust and user-friendly pricing tool in their app.

- ## Model Performance Analysis Based on RMSE & Execution Time

The results provide a detailed comparison of model accuracy (RMSE) and execution time (training and prediction).

- RMSE (Lower is Better)
    - Linear Regression: RMSE = 3609.58 → Worst RMSE (too simplistic, lacks flexibility).
    - Decision Tree Regression: RMSE = 2296.02 → Significant improvement over Linear Regression.
    - Random Forest Regression: RMSE = 2346.63 → Slightly worse than Decision Tree but provides more stability.
    - LightGBM: RMSE = 1725.01 → Best RMSE (Boosting worked extremely well).
    - LightGBM significantly outperformed all models, achieving the lowest RMSE (~1725), making it the best-performing model.

- Execution Time (Lower is Better)
    - Linear Regression: Fastest model (0.05s total), but poor accuracy.
    - Decision Tree Regression: Very fast (0.67s total) and performs much better than Linear Regression.
    - Random Forest Regression: Much slower (9.61s total), with no major RMSE improvement over Decision Tree.
    - LightGBM: Slowest model (20.79s total) but provides the best accuracy.
    - Takeaway:
        - LightGBM had the best prediction accuracy, but at the cost of a longer training time.
        - Decision Tree offered the best tradeoff between speed and accuracy.
        - Random Forest took much longer to train but didn’t significantly outperform Decision Tree.

- Final Verdict
    - Best Model: LightGBM → Achieved the lowest RMSE (1725.01), making it the most accurate.
    - Best Speed-Accuracy Tradeoff: Decision Tree Regression → Fast and still had a strong RMSE (2296.02).
    - Random Forest: Didn’t provide enough improvement over Decision Tree to justify its longer runtime.
 
## Overall Conclusion

The LightGBM (Gradient Boosted Regression) model was the best-performing model among the four tested. It provided the highest prediction accuracy (lowest RMSE) and outperformed the Random Forest model in both accuracy and training efficiency. While it required longer training time compared to Decision Tree Regression, the significant RMSE reduction (~570 points lower than Decision Tree) made the extra runtime worthwhile.

Despite LightGBM's strong performance, the dataset contains many categorical variables with high cardinality. Future improvements could include:
- Dimensionality Reduction Techniques: Feature selection or more efficient encoding strategies.
- Hyperparameter Tuning: More extensive tuning to optimize LightGBM parameters.
- Alternative Models: Exploring CatBoost or XGBoost to see if they can improve performance further.

Final Recommendation: LightGBM is the best model for Rusty Bargain’s used car price prediction, offering the most accurate valuation while balancing training and prediction time efficiently.
