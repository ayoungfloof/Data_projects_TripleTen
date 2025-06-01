## Basic Python: TV Ratings and Vote Distribution During the Golden Age

**Overview**

This project explores how audience voting behavior relates to show ratings during the so-called "Golden Age of Television" (1999–present). Using a dataset of movies and shows, the goal is to determine whether higher-rated TV shows also receive more audience votes, focusing exclusively on television content.

**Project Objective**
- Investigate whether highly rated TV shows also tend to receive more votes
- Focus only on shows released during the "Golden Age" (post-1999)
- Clean and prepare the dataset for reliable analysis
- Visualize rating and vote distribution across different score bands

**Data Sources**
- Dataset: movies_and_shows.csv
- Contains metadata on movies and shows (title, type, year, rating, number of votes)
- Initial data quality was unknown and required exploration and preprocessing

**Tools & Technologies**
- Language: Python
- Libraries: pandas, matplotlib, seaborn
- Environment: Jupyter Notebook

**Methodology**
1. Data Overview
- Loaded the dataset and reviewed key columns for completeness and consistency
- Identified missing or invalid values in rating and vote columns
2. Data Preprocessing
- Removed duplicate entries
- Filtered dataset to include only TV shows released after 1999
- Dropped entries with missing vote or rating values
- Validated remaining data distribution
3. Data Analysis
- Grouped shows by rating scores (0–10 scale)
- Aggregated and visualized total number of votes by rating
- Focused on identifying score ranges with the highest engagement (votes)

**Visuals**

![image](https://github.com/user-attachments/assets/aa5933f5-b861-4bfb-8999-92dac677cc7f)

**Conclusion**
- TV shows with higher ratings (particularly scores 7, 8, and 9) received the highest number of audience votes
- Shows with low ratings (0–3) had significantly less engagement
- Although there were some anomalies (e.g., score 4 had more votes than 5 or 6), the general trend supports the hypothesis
Approximately 94% of the original dataset was retained after preprocessing, giving confidence in the validity of the results.

