# Credit-Card-Customers-Prediction
This repository contains a Power BI dashboard for analyzing bank customer churn based on a dataset including features like attrition flags, customer demographics, card categories, income levels, credit limits, utilization ratios, and more. The dashboard visualizes key metrics and insights to identify churn patterns and inform retention strategies.
Project Overview
This repository contains a Power BI dashboard for analyzing bank customer churn based on a dataset including features like attrition flags, customer demographics, card categories, income levels, credit limits, utilization ratios, and more. The dashboard visualizes key metrics and insights to help identify churn patterns and inform retention strategies.
The dashboard is built using Power BI, with DAX formulas for KPIs and visualizations. You can import the .pbix file (if provided) or recreate it using the DAX code below.
Key Features

KPIs: Churn Rate, Average Customer Age, Total Active Customers, etc.
Charts: Bar charts for churn by card category, pie charts for churn by income, scatter plots for financial correlations.
Data Source: Assumes a table named 'BankChurners' (e.g., from CSV or Excel import).
Tools Used: Power BI Desktop.

Installation

Download Power BI Desktop from Microsoft's website.
Import your dataset (e.g., BankChurners.csv) into Power BI.
Create measures using the DAX code provided below.
Arrange visuals as per the layout suggestions in the previous conversation or based on the screenshot.

Dashboard Screenshot
Failed to load imageView link
(Upload the provided image as 'dashboard-screenshot.png' in your repo for reference.)
DAX Code
Below is the DAX code for key measures. You can copy-paste these directly into Power BI's "New Measure" dialog.
Churn Rate
textChurn Rate = 
DIVIDE(
    COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Attrited Customer")),
    COUNTROWS(BankChurners)
) * 100
Average Customer Age
textAvg Customer Age = AVERAGE(BankChurners[Customer_Age])
Total Active Customers
textTotal Active Customers = 
COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Existing Customer"))
Churn by Card Category
textChurn by Card Category = 
DIVIDE(
    CALCULATE(COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Attrited Customer"))),
    COUNTROWS(BankChurners)
)
Average Utilization Ratio
textAvg Utilization Ratio = AVERAGE(BankChurners[Avg_Utilization_Ratio])
Sum of Credit Limit
textSum of Credit Limit = SUM(BankChurners[Credit_Limit])
Churn Rate by Income Category
textChurn Rate by Income = 
DIVIDE(
    CALCULATE(COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Attrited Customer"))),
    CALCULATE(COUNTROWS(BankChurners))
) * 100
Additional Measures (from Behavioral Dashboard)
textAvg Months Inactive = AVERAGE(BankChurners[Months_Inactive_12_mon])
For full implementation, create visuals like:

Bar Chart: Churn Rate by Card_Category.
Pie Chart: Churn Rate by Income_Category.
Scatter Plot: Total_Revolving_Bal vs. Credit_Limit.

Usage

Load data into Power BI.
Add measures via Modeling > New Measure.
Drag fields to visuals and apply filters (e.g., slicers for Card_Category or Income_Category).

Contributing
Feel free to fork and submit pull requests for improvements, such as adding more DAX measures or ML integration for churn prediction.
