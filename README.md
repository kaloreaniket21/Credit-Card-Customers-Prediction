# 🏦 Credit Card Customer Churn Analytics Dashboard

[![Power BI](https://img.shields.io/badge/Data_Viz-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Excel](https://img.shields.io/badge/Data_Cleaning-MS%20Excel-217346?style=flat&logo=microsoftexcel&logoColor=white)](https://www.microsoft.com/excel)
[![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat&logo=kaggle&logoColor=white)](https://www.kaggle.com/)

An end-to-end descriptive and diagnostic analytics project built to identify high-risk credit card customers and uncover the driving factors behind customer attrition.

##  Project Overview
Customer attrition (churn) represents a massive loss in lifetime value for retail banks. This project analyzes a dataset of over 10,000 credit card customers to identify which demographic and financial segments are most likely to close their accounts. By transitioning from static spreadsheets to an interactive Power BI dashboard, the retention team can now pinpoint exactly *who* is leaving and *why*.

### Key Business Questions Answered:
* What is the overall customer churn rate?
* Which credit card tier (Platinum, Gold, Silver, Blue) experiences the highest attrition?
* How does income level correlate with a customer's likelihood to leave the bank?
* What is the relationship between credit utilization, revolving balances, and account closures?

---

##  Tech Stack & Workflow
* **Data Source:** `BankChurners` dataset from Kaggle.
* **Data Cleaning (ETL):** **Microsoft Excel** used to handle missing entries, standardize "Unknown" categorical values (e.g., in Education and Income), and format numerical financial columns.
* **Data Modeling:** **Power BI Desktop** used to establish data relationships and calculate custom DAX measures.
* **Visualization:** **Power BI** interactive dashboard featuring dynamic cross-filtering.

---
<img width="1413" height="777" alt="Screenshot 2026-03-05 164727" src="https://github.com/user-attachments/assets/1663359d-3076-418e-a62e-7ee61f9a86aa" />

##  Dashboard Highlights
The dashboard is designed for top-down executive analysis, moving from high-level KPIs to granular behavioral clusters:

1. **Top-Level KPIs:**
   * **Churn Rate:** 16.07%
   * **Total Active Customers:** 8,500
   * **Average Customer Age:** 46.33
   * **Sum of Avg Utilization Ratio:** 2.78K

2. **Demographic & Tier Breakdown:**
   * Bar charts detailing **Churn Rate by Card Category** (Platinum, Gold, Blue, Silver).
   * Horizontal bar charts mapping **Churn by Income Category**.
   * Donut/Pie charts visualizing the distribution of customer age and income brackets.

3. **Financial Behavior Analysis:**
   * A detailed scatter plot tracking the **Average Credit Limit vs. Total Revolving Balance**, segmented by Utilization Ratio, to identify high-risk debt clusters.

---

## Key Business Insights Discovered
* **The "Premium" Flight Risk:** Surprisingly, **Platinum** cardholders exhibit the highest relative churn rate (exceeding 20%), suggesting the bank's premium rewards program is failing to retain high-value clients compared to the highly stable Silver tier.
* **The Income Barbell Effect:** Customers in the highest income bracket (**$120K+**) and the lowest bracket (**Less than $40K**) are churning at the highest rates. The bank is simultaneously losing its wealthiest and most financially vulnerable segments.
* **Credit Utilization Risk:** Scatter plot analysis reveals specific clusters of customers with low credit limits but high revolving balances, indicating a segment of financially stressed customers at high risk of default or churn.

---

##  Core DAX Measures Used
To enable dynamic filtering, several custom DAX formulas were created. Examples include:

```dax
-- Calculating the Overall Churn Rate
Churn Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('BankChurners'), 'BankChurners'[Attrition_Flag] = "Attrited Customer"),
    COUNTROWS('BankChurners')
) * 100

-- Calculating Total Active Customers
Total Active Customers = 
CALCULATE(
    COUNTROWS('BankChurners'), 
    'BankChurners'[Attrition_Flag] = "Existing Customer"
)

```
##  Author
**Aniket Kalore** *Data Analyst*

📧 [kaloreaniket21@gmail.com](mailto:kaloreaniket21@gmail.com)  
🔗 [LinkedIn]( www.linkedin.com/in/aniket-kalore-9710712b0) 
     | [GitHub] https://github.com/kaloreaniket21

