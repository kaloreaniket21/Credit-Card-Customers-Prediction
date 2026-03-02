# Credit-Card-Customers-Prediction
This repository contains a Power BI dashboard for analyzing bank customer churn based on a dataset including features like attrition flags, customer demographics, card categories, income levels, credit limits, utilization ratios, and more. The dashboard visualizes key metrics and insights to identify churn patterns and inform retention strategies.
# Bank Customer Churn Analysis Dashboard

## Project Overview

This repository contains a Power BI dashboard for analyzing bank customer churn based on a dataset including features like attrition flags, customer demographics, card categories, income levels, credit limits, utilization ratios, and more. The dashboard visualizes key metrics and insights to help identify churn patterns and inform retention strategies.

The dashboard is built using Power BI, with DAX formulas for KPIs and visualizations. You can import the `.pbix` file (if provided) or recreate it using the DAX code below.

### Key Features
- **KPIs**: Churn Rate, Average Customer Age, Total Active Customers, etc.
- **Charts**: Bar charts for churn by card category, pie charts for churn by income, scatter plots for financial correlations.
- **Data Source**: Assumes a table named `'BankChurners'` (e.g., from CSV or Excel import).
- **Tools Used**: Power BI Desktop.

## Installation

1. Download Power BI Desktop 
2. Import your dataset (e.g., `BankChurners.csv`) into Power BI.
3. Create measures using the DAX code provided below.
4. Arrange visuals as per the layout suggestions in the previous conversation or based on the screenshot.

## Dashboard Screenshot

### <img width="1364" height="755" alt="Screenshot 2026-03-02 195812" src="https://github.com/user-attachments/assets/40b63a24-b1aa-4566-9e56-ca14cfdbcd67" />
 
*(Upload the provided image as `dashboard-screenshot.png` in your repo for reference.)*

## DAX Code

Below is the DAX code for key measures. You can copy-paste these directly into Power BI's "New Measure" dialog.

### Churn Rate
```dax
Churn Rate = 
### DIVIDE(
    COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Attrited Customer")),
    COUNTROWS(BankChurners)
) * 100
Feel free to fork and submit pull requests for improvements, such as adding more DAX measures or ML integration for churn prediction.

### Average Customer Age
daxAvg Customer Age = AVERAGE(BankChurners[Customer_Age])

### Total Active Customers
daxTotal Active Customers = 
COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Existing Customer"))

### Churn by Card Category
daxChurn by Card Category = 
DIVIDE(
    CALCULATE(COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Attrited Customer"))),
    COUNTROWS(BankChurners)
)
### Average Utilization Ratio
daxAvg Utilization Ratio = AVERAGE(BankChurners[Avg_Utilization_Ratio])

### Sum of Credit Limit
daxSum of Credit Limit = SUM(BankChurners[Credit_Limit])

### Churn Rate by Income Category
daxChurn Rate by Income = 
DIVIDE(
    CALCULATE(COUNTROWS(FILTER(BankChurners, BankChurners[Attrition_Flag] = "Attrited Customer"))),
    CALCULATE(COUNTROWS(BankChurners))
) * 100
