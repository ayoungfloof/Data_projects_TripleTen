# Optimizing Oil Well Locations for OilyGiant Mining Company

## Description:
This project aims to assist OilyGiant Mining Company in determining the optimal region for developing new oil wells. By leveraging geological exploration data, the goal is to identify the region with the highest potential profit while minimizing risks. Advanced machine learning techniques and statistical analysis will be applied to ensure an efficient and data-driven decision-making process.

## Objective:
- Train linear regression models to predict oil reserves for wells in each region.
- Evaluate the profitability of each region using predictions and business constraints.
- Perform risk analysis using bootstrapping to assess profit distributions and identify regions with acceptable risk thresholds.

## Data Sources:
Geological exploration data for three regions:

- geo_data_0.csv: Contains data for the first region.
- geo_data_1.csv: Contains data for the second region.
- geo_data_2.csv: Contains data for the third region.

Each dataset includes:

- id: Unique oil well identifier.
- f0, f1, f2: Three key features describing the well (specific meaning is not provided 
- product: Actual volume of reserves in the oil well (in thousand barrels).

## Approach:

Data Preparation:
- Load and inspect datasets for quality and completeness.
- Prepare the data for model training.

Model Development:
- Train a linear regression model for each region.
- Evaluate model performance using RMSE and average reserve predictions.

Profit Calculation:
- Estimate potential profit based on predictions and business constraints.

Risk Assessment:
- Apply bootstrapping to simulate profit distribution and evaluate risk levels.
- Identify regions with an acceptable risk threshold and the highest profit potential.

## Tools:

import pandas as pd
from sklearn.model_selection import train_test_split
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
from sklearn.metrics import mean_squared_error
import numpy as np

## Deliverables:

- Predictive models for oil reserves in each region.
- Profit and risk assessments based on model predictions and business conditions.
- A final recommendation on the feasibility of developing wells in each region.

This project will provide OilyGiant Mining Company with actionable insights, maximizing profit potential while adhering to acceptable risk levels.

### Overall Conclusion

This project aimed to identify the most profitable region for developing new oil wells for the OilyGiant mining company. By analyzing geological data from three regions, building predictive models, and conducting a profitability analysis, several key findings emerged:

Prediction Model Performance:
- Linear regression models were used to predict the reserves in each region.
- Average predicted reserves:
    - Region 0: 92.59 thousand barrels (RMSE: 37.58)
    - Region 1: 68.73 thousand barrels (RMSE: 0.89)
    - Region 2: 94.97 thousand barrels (RMSE: 40.03)
- Despite reasonable predictive accuracy, the models exhibited limitations, particularly with high RMSE values for Regions 0 and 2.

Profitability Analysis:
- Break-even volume per well: 111.11 thousand barrels.
- None of the regions achieved average reserves above the break-even point:
    - Region 0: 92.59 thousand barrels.
    - Region 1: 68.73 thousand barrels.
    - Region 2: 94.97 thousand barrels.
- All regions showed a negative average profit during the bootstrapping analysis:
    - Region 0: -\$17.10M
    - Region 1: -\$38.18M
    - Region 2: -\$14.65M
- Risk of loss was 100% for all regions, making the current development plan financially unviable under existing assumptions.

Assumptions and Business Constraints:
- Revenue was fixed at \$4,500 per thousand barrels.
- Cost per well was assumed to be \$500,000.
- Selection of the top 200 wells may not account for operational or spatial constraints.
- High RMSE values indicate potential limitations in the linear regression models used.

Recommendations:
1. Reassess Business Assumptions:
    - Review cost estimates and explore operational efficiencies to reduce costs.
    - Validate the fixed revenue per barrel assumption with current market data.
    - Introduce variability in revenue and cost scenarios to reflect real-world uncertainties.
    
2. Improve Prediction Models:
    - Test more advanced machine learning models, such as Random Forest or Gradient Boosting, to capture non-linear relationships in the data.
    - Engineer additional features or refine existing ones to improve prediction accuracy.
    
3. Alternative Strategies:
    - Explore hybrid well-selection strategies that combine predicted reserves and geographic or operational constraints.
    - Investigate scenarios with adjusted budgets or risk thresholds to identify feasible options.
    
4. Conduct Further Risk Analysis:
    - Perform sensitivity analysis to evaluate the impact of changes in key variables (e.g., cost, revenue, reserve thresholds) on profitability.
    
    
Under the current assumptions, none of the regions are profitable for well development due to high costs and low reserves relative to the break-even point. Significant adjustments to business assumptions, operational strategies, or predictive models are required before proceeding with well development.
