# 🚀 Marketing A/B Testing Analysis

[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-blue?style=for-the-badge&logo=kaggle)](https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing/data)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)

An end-to-end analytical workflow to evaluate marketing campaign effectiveness, utilizing rigorous statistical hypothesis testing and bias adjustment to drive data-driven decision making.

---

## 📑 Table of Contents
* [📌 Project Overview](#-project-overview)
* [📊 Data Source](#-data-source)
* [🛠 Tech Stack](#-tech-stack)
* [🔍 Methodology](#-methodology)
* [💡 Actionable Recommendations](#-actionable-recommendations)

---

## 📌 Project Overview
This project conducts a comprehensive A/B testing analysis of a marketing campaign to evaluate whether a new advertisement significantly improves user conversion rates. The workflow covers:
* **Data Cleaning & Profiling**
* **Exploratory Data Analysis (EDA)**
* **Rigorous Statistical Hypothesis Testing**
* **Bias Adjustment & Business Impact Assessment**

---

## 📊 Data Source
The dataset used in this analysis is the **Marketing A/B Testing** dataset provided by Favio Vázquez, hosted on Kaggle.
* **Dataset Link:** [Kaggle - Marketing A/B Testing](https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing/data)

---

## 🛠 Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Statistical Analysis:** SciPy (`chi2_contingency`, `ttest_ind`), Statsmodels (Logistic Regression, Two-Way ANOVA)
* **Data Visualization:** Matplotlib, Seaborn

---

## 🔍 Methodology

### 1. Data Profiling & Cleaning
* Validated data integrity and handled duplicate User IDs.
* **Outlier Handling:** Filtered out the top 1% of users with abnormally high ad exposures (`total ads`) to mitigate bot interference and prevent skewed averages.

### 2. Exploratory Data Analysis (EDA)
* Analyzed sample size balance: Ad group (96%) vs. PSA group (4%).
* Despite the imbalance, the control group (23,000+ users) provided sufficient statistical power for robust testing.

### 3. Statistical Hypothesis Testing
* **Sanity Check (T-test):** Identified a potential sampling bias in `most ads hour`.
* **Chi-Square Test:** Resulted in a p-value of **1.13e-14**, leading to the **rejection of the null hypothesis** and suggesting the ad has a strong positive impact on conversion.

### 4. Adjusting for Bias (Logistic Regression)
* Implemented a **Logistic Regression** model to control for confounding variables (e.g., time of day).
* **Robust Results:** The p-value remained highly significant (**3.16e-14**), confirming the ad campaign genuinely drives higher conversions even after bias adjustment.

### 5. Time-Based Optimization (Two-Way ANOVA)
* Investigated the combined effect of "Day of the Week" and "Time of Day" on conversions.
* Validated that temporal targeting is crucial for campaign efficiency.

### 6. Business Impact & Lift Analysis
* Calculated **Absolute and Relative Lift** to estimate potential incremental conversions and revenue potential for stakeholders.

---

## 💡 Actionable Recommendations
1. **Full-Scale Rollout:** Confidently deploy the new ad campaign based on strong statistical evidence.
2. **Dynamic Budget Allocation:** Adjust marketing budgets across different days to align with user responsiveness.
3. **Dayparting Bidding Strategy:** Focus ad spend during "Golden Hours" to maximize ROI and reduce CPA.

---
*Developed by Chitnapak Kingkoyao*
