# Optimizing Gold Recovery Process for Efficient Mining Operations

**Overview**

This project supports a mining operation in improving the efficiency of its gold recovery process through data analysis and machine learning. By analyzing metal concentrations, process parameters, and equipment stages, we developed a predictive model that estimates recovery rates. This enables the operation to make data-driven decisions, optimize resource allocation, and improve yield across flotation and purification stages.

**Project Objective**
- Validate recovery calculation logic and prepare data for modeling
- Explore patterns in metal concentration, particle size, and anomalies
- Build and evaluate regression models using sMAPE as the main metric
- Tune and test the model on unseen data for final evaluation
- Translate technical findings into actionable business insights
    
**Data Sources**
The data provided comes from a mining operation and is structured into three datasets:
- Training Dataset: Contains historical data for model training.
- Test Dataset: Includes unseen data for evaluating model performance.
- Full Dataset: Combines training and test data for exploratory analysis.

**Tools & Technology**
- Python Libraries: pandas, NumPy, matplotlib, seaborn, scikit-learn
- Models: Random Forest, Decision Tree, Linear Regression, Dummy Regressor
- Validation: KFold cross-validation, GridSearchCV, custom sMAPE scorer
- Metric: Symmetric Mean Absolute Percentage Error (sMAPE)

**Methodology**
1. Data Preprocessing & Feature Engineering
- Validated and corrected recovery formula for rougher stage
- Removed irrelevant features (e.g., date, duplicate columns)
- Filled missing values and ensured alignment between training and test sets
- Engineered features based on metal concentration and process consistency
2. Exploratory Data Analysis
- Confirmed expected concentration trends:
- Gold increased through each stage (feed → rougher → final)
- Silver and lead decreased, reflecting purification effects
- Particle size distributions were consistent between train/test sets
- Identified and addressed anomalies in metal totals
- Explored relationships between reagent use, air flow, and recovery efficiency
3. Model Training & Evaluation
- Model	sMAPE (Combined)
- Decision Tree	19.60
- Linear Regression	12.66
- Random Forest	12.06
- Final Random Forest model tuned via cross-validation
- Evaluation on test set produced a final sMAPE of 10.67
- Dummy Regressor used as a baseline (sMAPE: 10.35)

**Visuals**

![image](https://github.com/user-attachments/assets/36dfaf5d-d0b9-4d25-a83d-92ed158ae5f9)

![image](https://github.com/user-attachments/assets/76ed4143-63bf-40fd-a2d2-ab334f98b98f)

![image](https://github.com/user-attachments/assets/24f9ebf6-bb3c-44be-ae85-684d571f394f)

![image](https://github.com/user-attachments/assets/683bc920-0244-49ea-ab59-1b524b29798d)

![image](https://github.com/user-attachments/assets/64dd6fdc-9934-4206-96b2-3a7a2c8afc4d)

![image](https://github.com/user-attachments/assets/3626b0fe-b75a-41d0-b864-3f9596b66253)

![image](https://github.com/user-attachments/assets/c28b40b1-94ff-464e-b66e-42663603128b)

**Conclusion**
The final tuned Random Forest Regressor achieved a sMAPE of 10.67, outperforming its untuned version (12.06) and demonstrating strong predictive capabilities. While the Dummy Regressor had a slightly lower sMAPE (10.35), the Random Forest model captured important nonlinear relationships and provided more reliable recovery estimates.

**Business Impact & Recommendations**
- The model enables real-time forecasting of gold recovery at multiple process stages
- Can be integrated into monitoring systems to trigger process adjustments based on predicted output
- Helps minimize waste, optimize reagent use, and maximize yield
- Next Steps:
    - Apply advanced feature selection and ensemble tuning for further gains
    - Consider adding real-time sensor feeds to extend predictive value
    - Deploy as a component in an AI-assisted mining control platform

**Final Takeaway**
This project illustrates how machine learning can support intelligent decision-making in resource-heavy industries. By combining domain-specific metrics like sMAPE with robust modeling techniques, mining operations can drive measurable efficiency improvements in gold recovery.
