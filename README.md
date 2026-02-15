# Sales Performance Dashboard (Power BI)
# Project Overview

This project analyzes sales performance, profit trends, discount impact, and store-type comparison using Power BI.

# Business Problem

The company wants to:

Compare performance across store types

Identify high-performing stores and product types

Understand how discounts impact profit


# Dashboard Features

Sales vs Target 

Monthly sales and Profit performance over time

Discount impact visualization

Store type performance comparison

KPI cards (Total Sales, Profit, Quantity, Return rate)


# DAX Measures Used
CALCULATE(
   SUM(Sales[SalesAmount]),
    DATESBETWEEN(
        Sales[DateKey],
        DATE(2025, 1, 1),
        DATE(2025, 4, 30)
    )
)
SalesQTY (2025) = 
CALCULATE(
   SUM(Sales[SalesQuantity]),
    DATESBETWEEN(
        Sales[DateKey],
        DATE(2025, 1, 1),
        DATE(2025, 4, 30)
    )
)
ReturnRate (2025) = 
CALCULATE(
   AVERAGE(Sales[ReturnRate]),
    DATESBETWEEN(
        Sales[DateKey],
        DATE(2025, 1, 1),
        DATE(2025, 4, 30)
    )
)
Profit (2025) = 
CALCULATE(
    SUM(Sales[SalesAmount])-SUM(Sales[TotalCost]),
    DATESBETWEEN(
        Sales[DateKey],
        DATE(2025, 1, 1),
        DATE(2025, 4, 30)
Monthly sales/Stock ratios = CALCULATE(SUM(Stores[SalesLast30d])/SUM(Stores[Stock]))
Profit margin = Sales[ProfitNew] / Sales[SalesAmount]
ReturnRate = Sales[ReturnAmount] / Sales[SalesAmount]
Year sale = CALCULATE(SUM(Sales[SalesAmount]),YEAR(Sales[DateKey]))

# Tools Used

Excel

Power BI

DAX

Data Modeling

Data Cleaning
