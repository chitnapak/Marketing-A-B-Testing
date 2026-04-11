# 🚀 Marketing A/B Testing Analysis

## 📌 Project Overview
This project conducts a comprehensive A/B testing analysis of a marketing campaign to evaluate whether a new advertisement significantly improves user conversion rates. The end-to-end analytical workflow covers data cleaning, exploratory data analysis (EDA), rigorous statistical hypothesis testing, and business impact assessment. The ultimate goal is to translate data into actionable insights for strategic marketing optimization.

## 🛠 Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Statistical Analysis:** SciPy (`chi2_contingency`, `ttest_ind`), Statsmodels (Logistic Regression, Two-Way ANOVA)
* **Data Visualization:** Matplotlib, Seaborn

## 🔍 Methodology

### 1. Data Profiling & Cleaning
* Validated data integrity and handled duplicate User IDs.
* **Outlier Handling:** Filtered out the top 1% of users with an abnormally high number of ad exposures (`total ads`) to mitigate bot interference and prevent skewed statistical averages.

### 2. Exploratory Data Analysis (EDA)
* Analyzed sample size balance: The treatment group (Ad group) accounted for 96% of the data, while the control group (PSA group) accounted for 4%.
* Despite the imbalance, the control group contained over 23,000 users, providing sufficient statistical power for robust testing.

### 3. Statistical Hypothesis Testing
* **Sanity Check (T-test):** Evaluated user behavior regarding the peak ad exposure hour (`most ads hour`) between the two groups. A significant difference was found, indicating a potential sampling bias that required careful handling in subsequent steps.
* **Chi-Square Test:** Assessed the relationship between group assignment and conversion. The resulting p-value (1.13e-14) led to the **rejection of the null hypothesis**, suggesting a strong positive impact of the ad on conversion rates.

### 4. Adjusting for Bias (Logistic Regression)
* Due to the failed sanity check, a **Logistic Regression** model was implemented to control for confounding variables, specifically adjusting for the "time of day" factor.
* **Robust Results:** Even after accounting for time bias, the p-value remained highly significant (3.16e-14), confirming that **the ad campaign genuinely drives higher conversions.**

### 5. Time-Based Optimization (Two-Way ANOVA)
* Utilized **Two-Way ANOVA** to investigate the combined effect of "Day of the Week" and "Time of Day" on conversions.
* **Findings:** Both factors showed statistically significant impacts (p-values nearing 0), validating the hypothesis that dayparting and temporal targeting are crucial.

### 6. Business Impact & Lift Analysis
* Evaluated the economic value of the campaign by calculating **Absolute and Relative Lift**.
* Estimated the potential incremental conversions, providing stakeholders with a clear view of the revenue potential for scaling the campaign.

## 💡 Actionable Recommendations
1. **Full-Scale Rollout:** Confidently deploy the new ad campaign to the entire user base, as statistical evidence strongly supports its superior performance in driving conversions compared to the control group.
2. **Dynamic Budget Allocation:** Adjust marketing budgets dynamically across different days of the week to align with actual user responsiveness and conversion trends.
3. **Dayparting Bidding Strategy:** Focus ad spend during the identified "Golden Hours" to maximize Return on Investment (ROI) and significantly reduce the Cost-Per-Acquisition (CPA).
