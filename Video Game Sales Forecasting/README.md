## Video Game Sales Analysis and Insights

**Overview**

This project analyzes historical video game sales data to uncover the key factors influencing game success. By evaluating sales trends, user and critic ratings, and regional preferences, the goal is to generate actionable insights that support marketing decisions for Ice, an online video game store.

**Project Objective**
- Analyze sales trends across platforms and genres
- Explore the relationship between critic/user ratings and sales
- Identify regional differences in genre and platform popularity
- Test hypotheses on user rating distributions across categories
- Inform future game marketing strategies based on insights

**Dataset Source**
- Dataset Source: Open-source dataset (e.g., Kaggle)
- Time Range Analyzed: 2012–2016 (filtered for relevance and reliability)
- The dataset used in this analysis comes from open sources such as Kaggle, covering video game sales, ratings, and reviews from 1980 to 2016.
- Data Description
  - **Name**: The name of the game
  - **Platform**: The gaming console/platform (e.g., Xbox, PlayStation)
  - **Year_of_Release**: The year the game was released
  - **Genre**: The genre of the game (e.g., Action, Sports)
  - **NA_sales**: Sales in North America (in million USD)
  - **EU_sales**: Sales in Europe (in million USD)
  - **JP_sales**: Sales in Japan (in million USD)
  - **Other_sales**: Sales in other countries (in million USD)
  - **Critic_Score**: Average critic score (maximum of 100)
  - **User_Score**: Average user score (maximum of 10)
  - **Rating**: ESRB rating (e.g., E for Everyone, T for Teen)

**Tools & Technologies**
- Languages: Python (pandas, NumPy, SciPy)
- Visualization: matplotlib, seaborn, plotly
- Modeling: None (Exploratory Data Analysis and Hypothesis Testing)
- Evaluation: t-test (scipy.stats.ttest_ind), correlation analysis
- Tuning: Not applicable for this exploratory project

**Methodology**
1. Data Preparation
- Filtered dataset to include relevant years (2012–2016)
- Removed missing or anomalous values
- Standardized score scales and normalized categorical variables
2. Exploratory Analysis
- Analyzed annual game release trends and regional sales distributions
- Compared platform and genre performance by region
- Evaluated the distribution and central tendency of critic/user scores
- Assessed ESRB rating popularity across geographic markets
3. Hypothesis Testing
- Two t-tests were conducted:
- User Scores: Xbox One vs. PC
- Result: No significant difference
- Interpretation: User satisfaction is comparable across these platforms
- User Scores: Action vs. Sports Games
- Result: Statistically significant difference
- Interpretation: User ratings vary between these genres, suggesting different engagement levels
4. Correlation Analysis
- Moderate positive correlation found between critic scores and game sales (especially on PS4 and Xbox One)
- Weak or negligible correlation between user scores and sales, implying limited influence on purchasing behavior

**Results & Insights**
- Platform Performance
  - North America: Xbox 360, PS4, and PS3 were top performers
  - Europe: PS4, PS3, and Xbox 360 dominated
  - Japan: 3DS led by a large margin, followed by PS3 and PS4
 
**Genre Trends**
- Top Genres: Action, Shooter, Role-Playing (by total and average sales)
- Platform Games: Highest median sales despite fewer releases
- Underperforming Genres: Adventure and Strategy showed niche appeal

**Regional Preferences**
- North America:
  - Platform Leaders: Xbox 360, PS4, PS3
  - Top Genres: Action, Sports, Shooter
  - ESRB Preferences: 'M' (Mature)
- Europe:
  - Platform Leaders:	PS4, PS3, Xbox 360
  - Top Genres:	Action, Sports, Shooter
  - ESRB Preferences:	'M' and 'T' (Teen)
- Japan:
  - Platform Leaders: 3DS, PS3, PS4
  - Top Genres:	Role-Playing, Action
  - ESRB Preference:	'E' (Everyone), 'T'
 
**Conclusion**
This analysis offers key insights to guide Ice’s game marketing and inventory planning:
- Genre Focus: Prioritize Action, Shooter, and Role-Playing games
- Platform Strategy: Invest in titles for PS4 and Xbox One, which retain strong user bases
- Regional Customization: Tailor content to match local preferences (e.g., mature games in NA/EU, family-friendly in Japan)
- Critic Reviews: Leverage professional reviews for promotional campaigns, especially on consoles
- Genre-Specific Messaging: Acknowledge that different genres yield different user reception, influencing engagement
