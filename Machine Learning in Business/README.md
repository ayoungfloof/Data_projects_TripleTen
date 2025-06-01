## Optimizing Oil Well Locations for OilyGiant Mining Company

**Project Overview**
This project supports OilyGiant, a resource extraction company, in selecting the most promising region for oil well development. Using geological data and predictive modeling, the goal is to evaluate the profitability and risk for three candidate regions and recommend the optimal investment strategy

**Objectives**
- Train linear regression models to predict oil reserves in each region
- Estimate profitability based on predictions, revenue per barrel, and operational costs
- Assess financial risk using bootstrapping and statistical confidence intervals
- Recommend the most viable region for development (if any) based on performance and risk

**Data Sources**
- Geological exploration data for three regions:
    - geo_data_0.csv: Contains data for the first region.
    - geo_data_1.csv: Contains data for the second region.
    - geo_data_2.csv: Contains data for the third region.
Each dataset includes:
- id: Unique oil well identifier.
- f0, f1, f2: Three key features describing the well (specific meaning is not provided 
- product: Actual volume of reserves in the oil well (in thousand barrels).

**Tools & Technologies**
- import pandas as pd
- import numpy as np
- from sklearn.linear_model import LinearRegression
- from sklearn.metrics import mean_squared_error
- from sklearn.model_selection import train_test_split
- import matplotlib.pyplot as plt
- import seaborn as sns

**Methodology**
1. Data Preparation
- Loaded and cleaned data from each region
- Split into training/validation sets
- Verified absence of missing values or anomalies
2. Model Training
- Trained a Linear Regression model per region
- Evaluated with RMSE and average reserve estimates
3. Profit & Risk Analysis
- Profit formula:
- profit = (predicted reserves × $4500) - $500,000 per well
- Used bootstrapping with 1000 samples to simulate profit distributions
- Evaluated:
    - Average profit across top 200 wells
    - 95% confidence interval
    - Risk of loss

**Visuals**

![image](https://github.com/user-attachments/assets/43322633-6d60-4a4d-8761-f7316e6d4670)

![image](https://github.com/user-attachments/assets/531c9076-b05f-45fd-beac-83e7af81f497)

![image](https://github.com/user-attachments/assets/0f04af79-fc28-4f53-ac84-5eb1891f2bfe)

![image](https://github.com/user-attachments/assets/82123365-af29-4816-af18-e644fe82c8bb)

![image](https://github.com/user-attachments/assets/e10e85cc-42e9-4b4c-814b-fee7af5abdc3)

![image](https://github.com/user-attachments/assets/d18a6232-6856-4c8d-87e7-92d6bdb1cd4e)

![image](https://github.com/user-attachments/assets/d9904159-367e-44a7-9df7-0fc771dfd1f3)

![image](https://github.com/user-attachments/assets/f9839c5a-369a-450a-88ae-7dc46d5ab283)

![image](https://github.com/user-attachments/assets/31d67e2a-6043-4b22-b840-482806500f3d)

![image](https://github.com/user-attachments/assets/c078cc2e-38b0-4c60-94fe-052db9ee56ce)

![image](https://github.com/user-attachments/assets/cf2eb9e0-c92b-4f67-9489-49ec0270951f)

![image](https://github.com/user-attachments/assets/7803b0e8-948d-4766-8708-e7af4cf39b1c)

**Key Findings**
- Model Performance
- Region |	Average Predicted Reserves |	RMSE:
    - 0	92.59 thousand barrels	37.58
    - 1	68.73 thousand barrels	0.89
    - 2	94.97 thousand barrels	40.03
Note: Region 1 had the lowest error, but also the lowest reserves.
- Profitability & Risk
- Region |	Avg. Profit (Top 200 Wells) |	95% CI |	Risk of Loss:
    - 0	-$17.10M	-$34.4M to $0.6M	100%
    - 1	-$38.18M	-$43.5M to -$33.5M	100%
    - 2	-$14.65M	-$29.6M to $0.1M	100%
- None of the regions exceed the break-even point of 111.11k barrels per well
- All regions show 100% risk of loss under current assumptions

**Assumptions**
- Revenue = $4500 per 1000 barrels
- Cost per well = $500,000
- Top 200 wells selected per region
- Linear modeling only (no nonlinear regressors or feature engineering applied)

**Recommendations**
- Revisit Business Assumptions
    - Validate fixed revenue per barrel against market volatility
    - Explore operational cost reductions or variable well selection strategies
- Improve Model Accuracy
    - Test advanced models (e.g., Random Forest, Gradient Boosting)
    - Engineer domain-specific features if geological expertise is available
- Adjust Strategy
    - Pause well development under current strategy
    - Consider phased exploration or pilot wells with reevaluation after partial deployment

 **Final Verdict**
- No region meets profitability or risk tolerance thresholds.
- Major improvements in cost structure, modeling accuracy, or market conditions are needed before development can proceed.
- This project demonstrates the power of data science in business planning — helping avoid multi-million dollar losses through robust modeling and simulation.
