## Optimizing Used Car Price Predictions for Rusty Bargain

**Overview**
Rusty Bargain, a used car sales service, is developing an app to help customers quickly estimate the market value of their vehicles. This project leverages historical car data to build a machine learning model that predicts car prices accurately and efficiently — balancing performance with computational cost for real-time usage.

**Project Objective**
- Build regression models to predict used car prices
- Compare performance across Linear Regression, Decision Tree, Random Forest, and LightGBM
- Optimize hyperparameters using Optuna
- Evaluate accuracy, training time, and inference speed
- Recommend the best model for production deployment in the pricing app

**Data Sources**
- Dataset path: /datasets/car_data.csv
- The dataset contains detailed information about used cars, stored in /datasets/car_data.csv, with the following key features:
    - Vehicle characteristics: VehicleType, RegistrationYear, Gearbox, Power, Mileage, FuelType, Brand, Model, NotRepaired
    - Listing details: DateCrawled, DateCreated, LastSeen, NumberOfPictures, PostalCode
    - Target variable: Price (in Euros)

**Tools & Technologies**
- Languages: Python (pandas, NumPy, scikit-learn, lightgbm, optuna)
- Visualization: matplotlib, seaborn, plotly
- Modeling: Linear Regression, Decision Tree, Random Forest, LightGBM
- Evaluation: RMSE, Training Time, Inference Time
- Tuning: Optuna

**Methodogy**
1. Data Preparation
- Loaded and explored data
- Handled missing values and removed irrelevant features
- Encoded categorical variables
- Performed train/validation/test split
2. Model Training
- Baseline model: Linear Regression
- Trained advanced models: Decision Tree, Random Forest, LightGBM
- Applied Optuna for hyperparameter tuning (especially for LightGBM)
3. Evaluation Metrics
- Root Mean Squared Error (RMSE): primary metric for accuracy
- Recorded training time and prediction latency for each model

**Results & Comparison**
- Model |	RMSE:
    - Linear Regression	3609.58
    - Decision Tree	2296.02
    - Random Forest	2346.63
    - LightGBM	1725.01
- LightGBM outperformed all other models with the lowest RMSE.

**Execution Time**
- Model |	Training + Inference Time:
    - Linear Regression	0.05s (Fastest)
    - Decision Tree	0.67s
    - Random Forest	9.61s
    - LightGBM	20.79s (Slowest)
- Decision Tree provided a strong balance of speed and accuracy.
- LightGBM required more time but delivered significantly better predictions.

**Final Verdict**
- Category | Winner:
    - Best Accuracy	- LightGBM
    - Best Speed - Linear Reg.
    - Best Trade-off Model	-  Decision Tree
- LightGBM is the best model for deployment based on RMSE
- Decision Tree may be suitable for faster predictions with reasonable accuracy
- Random Forest added training time without substantial performance gain

**Recommendations**
- Deploy LightGBM in the Rusty Bargain app for optimal price predictions
- Explore CatBoost or XGBoost for further accuracy or efficiency gains
- Apply dimensionality reduction (e.g., PCA) or more efficient encoding for large-scale deployment
- Enhance Optuna tuning with longer trials and early stopping

**Conclusion**

This project demonstrates the impact of model choice and optimization techniques on predictive performance. By testing multiple models and tuning them with Optuna, we achieved a highly accurate price prediction model ready for integration into Rusty Bargain’s pricing platform.
