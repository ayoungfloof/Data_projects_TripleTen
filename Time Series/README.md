##  Forecasting Hourly Taxi Demand for Sweet Lift Taxi

**Overview**
Sweet Lift Taxi, a ride-hailing service operating around major airports, aims to improve operational efficiency by accurately forecasting the number of taxi orders for the upcoming hour. This time series forecasting project leverages historical demand data to predict hourly order volume, helping the company manage driver allocation more effectively. The performance benchmark was an RMSE (Root Mean Squared Error) below 48 on unseen data.

**Project Objective**
- Build and compare multiple forecasting models for hourly taxi demand
- Evaluate both traditional time series (ARIMA) and modern machine learning models (Random Forest, LightGBM, CatBoost, XGBoost)
- Engineer time-based features (lag, rolling mean, calendar variables)
- Tune hyperparameters to optimize predictive performance
- Select the best model based on RMSE and forecast reliability
- Visualize predictions and support real-time decision-making

**Data Sources**
- Dataset Path: /datasets/taxi.csv
- The dataset includes hourly historical taxi order data with:
    - datetime: Timestamp for each record (hourly)
    - num_orders: Number of taxi orders placed in each hour
    
**Tools & Technologies**
- Languages: Python (pandas, NumPy, scikit-learn, statsmodels)
- Visualization: matplotlib, seaborn
- Modeling: Linear Regression, Random Forest, LightGBM, CatBoost, XGBoost, ARIMA
- Evaluation: RMSE
- Tuning: Manual + Grid search for best parameters

**Methodology**
1. Data Preparation
- Resampled data to ensure hourly granularity
- Conducted time series decomposition to observe trend and seasonality
- Used ADF test to confirm non-stationarity and applied differencing
- Created lag features, rolling mean features, and datetime-based features (hour, day of week)
- Used chronological train/validation/test splits (10% of data reserved for testing)
2. Model Training
- Trained the following models:
- Linear Regression (baseline)
- Random Forest Regressor
- LightGBM Regressor
- CatBoost Regressor
- XGBoost Regressor
- ARIMA
- Applied hyperparameter tuning for models with significant promise (LightGBM, CatBoost).
3. Evaluation Metrics
- Root Mean Squared Error (RMSE) used as primary metric
- Visualization of predicted vs actual values to assess fit
- Plotted line graphs and seasonal patterns to confirm prediction stability

**Visuals**

![image](https://github.com/user-attachments/assets/061aced0-b20f-4d5f-86da-df01052350f5)

![image](https://github.com/user-attachments/assets/61cc5b47-82de-4370-a75c-969b278cf58d)

![image](https://github.com/user-attachments/assets/6725c0b5-1046-40fd-98b8-d18d4aabc92b)

![image](https://github.com/user-attachments/assets/7439cbbe-5e01-4837-ac1b-b32fd90be95d)

**Results & Comparison**
- Linear Regression -	50.31
- Random Forest -	45.11
- CatBoost -	43.71
- XGBoost -	46.05
- LightGBM -	43.66 (initial)
- LightGBM (Tuned) -	24.87
- ARIMA	67.06 -
- LightGBM provided the best balance of speed and accuracy
- ARIMA underperformed, likely due to underfitting and lack of feature flexibility

**Tuned LightGBM Parameters**
- n_estimators = 100
- max_depth = 10
- num_leaves = 31
- learning_rate = 0.1
- This configuration reduced RMSE to 24.87, well below the target threshold of 48.

**Final Verdict**
- Best Accuracy	LightGBM (Tuned)
- Best Simplicity (Baseline)	Linear Regression
- Weakest Fit	ARIMA
- Deploy the tuned LightGBM model for operational forecasting
- Reserve simpler models for baseline or interpretability needs

**Recommendations**
- Integrate the tuned LightGBM model into Sweet Lift’s real-time dispatching system
- Explore further tuning with cross-validation over multiple seasonal cycles
- Consider adding external features (e.g., weather, events, flight schedules) for enhanced predictions
- Revisit ARIMA with SARIMA variants for improved seasonality modeling

**Conclusion**

This project successfully forecasted hourly taxi demand using a variety of modeling techniques. The tuned LightGBM model achieved an RMSE of 24.87, significantly outperforming the benchmark. With proper integration, this model can help Sweet Lift Taxi proactively allocate drivers, reduce wait times, and optimize service availability.
