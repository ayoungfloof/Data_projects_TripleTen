## General conclusion
The main goal of this project was to analyze user behavior across two different prepaid plans (Surf and Ultimate) offered by Megaline, and determine which plan generates more revenue.

Several datasets were provided, including user data, call records, message logs, and internet usage.
Key cleaning steps included handling missing values, converting date columns to datetime types, and filtering out irrelevant data (such as calls with zero duration and internet sessions with zero traffic).
Additional columns were added to enrich the data, such as user churn status, tenure (subscription duration), and indicators for users who exceeded their plan limits.

Data was aggregated at the user-month level to calculate monthly totals for calls, messages, and internet usage. This allowed for a better comparison between users and plans on a monthly basis.

Calls: The analysis showed that Ultimate plan users tend to make longer and more variable calls compared to Surf users. Ultimate users, with their larger included minutes, made longer calls on average.

Messages: Ultimate plan users also tend to send more messages than Surf users. Surf plan users were constrained by their lower message limit, which likely influenced their behavior.

Internet Usage: Users on the Surf plan consistently consumed more internet data than Ultimate users, which could indicate that Surf users are more likely to exceed their data limit and incur extra charges.

The revenue analysis revealed that, on average, the Ultimate plan generates more revenue per user than the Surf plan. This is largely due to the higher monthly subscription fee and additional charges incurred by users who exceed their plan's limits (especially for calls and data).However, Surf plan users who exceeded their limits for messages and internet data also contributed significantly to revenue through extra charges.

Plan Revenue Comparison: A hypothesis test was conducted to compare the average revenue from Surf and Ultimate users. The results showed a statistically significant difference, with Ultimate users generating more revenue on average.

Regional Revenue Comparison: Another hypothesis test was conducted to compare the average revenue from users in the NY-NJ area versus users from other regions. This test also showed a statistically significant difference, with NY-NJ users generating more revenue on average, possibly due to higher usage patterns in this metropolitan area.

Key Take Aways: The Ultimate plan is more profitable overall due to its higher base subscription fee and the tendency of users to exceed their call and data limits.Surf users, while paying less in base fees, often exceed their message and data limits, which contributes to additional revenue, though not as much as Ultimate users.Regional differences suggest that NY-NJ area users contribute more revenue, potentially indicating higher usage or different usage patterns in this metropolitan area.

Recommendations:Based on this analysis, Megaline could consider adjusting its marketing strategies to focus on promoting the Ultimate plan, as it generates higher revenue per user.Additionally, the company might explore offering a mid-tier plan that bridges the gap between Surf and Ultimate, catering to users who consistently exceed their limits but might not need the full benefits of the Ultimate plan.
