Power BI Assignment – DAX & Data Visualization

📌 Project Overview

This project focuses on analyzing an E-Commerce Sales Dataset using Microsoft Power BI. The objective is to apply Data Analysis Expressions (DAX) to create calculated columns and measures, build interactive visualizations, and generate meaningful business insights related to sales performance, profitability, order trends, and sales target achievement.

This project continues the previous Power BI assignment on data import, transformation, data cleaning, aggregation, and data modeling.

🎯 Project Objectives

Create calculated columns using DAX.

Develop measures to calculate important business metrics.

Analyze sales, profit, quantity, and order performance.

Compare actual sales against sales targets.

Identify monthly sales trends and regional sales patterns.

Build interactive dashboards for business reporting.

Present data-driven insights through effective visualizations.

🗂️ Dataset Description

The project uses three datasets:

1. List of Orders

Contains order-level and customer-related information.

Key columns: Order ID, Order Date, Customer Name, City, State, Category, Amount, Profit.

2. Order Details

Contains product category and order-level sales information.

Key columns: Order ID, Category, Sub-Category, Quantity, Amount, Profit.

3. Sales Target

Contains monthly sales target information.

Key columns: Category, Month of Order Date, Target.

🛠️ Tools & Technologies

Microsoft Power BI Desktop

Power Query Editor

DAX (Data Analysis Expressions)

Data Modeling and Relationships

Data Visualization

GitHub for project documentation and version control

⚙️ Project Workflow

1. Data Preparation and Modeling

Imported the datasets into Power BI.

Applied data transformation and formatting in Power Query.

Corrected data types and standardized text fields.

Created calculated columns where required.

Merged related tables using Order ID where appropriate.

Established relationships between the relevant tables.

Prepared the data model for DAX calculations and reporting.

2. DAX Calculations

Calculated Columns

Category Type

Combines Category and Sub-Category into a single column.

Category Type =
'Order Details'[Category] & " - " &
'Order Details'[Sub-Category]

Revenue per Order

Calculates revenue by multiplying Amount by Quantity, as specified in the assignment.

Revenue per Order =
'Order Details'[Amount] *
'Order Details'[Quantity]

Sales Category

Classifies sales amounts as Above Average or Below Average. Values equal to the average are classified as Below Average in this example.

Sales Category =
IF(
    'Order Details'[Amount] >
        CALCULATE(
            AVERAGE('Order Details'[Amount]),
            ALL('Order Details')
        ),
    "Above Average",
    "Below Average"
)

Calculated Measures

Order Count

Counts distinct orders to avoid counting the same order multiple times.

Order Count =
DISTINCTCOUNT('Order Details'[Order ID])

Average Profit in Delhi

Calculates average profit for orders placed in Delhi.

Average Profit in Delhi =
CALCULATE(
    AVERAGE('List of Orders'[Profit]),
    'List of Orders'[City] = "Delhi"
)

Total Sales

Total Sales =
SUM('List of Orders'[Amount])

Total Sales Target

Total Sales Target =
SUM('Sales Target'[Target])

Year-to-Date (YTD) Sales

Assuming a properly configured Date table related to the order date:

YTD Sales =
TOTALYTD(
    [Total Sales],
    'Date'[Date]
)

A continuous Date table marked as a date table is recommended for reliable time-intelligence calculations. The Date table and relationships should be adjusted to match the actual Power BI model.

📊 Data Visualizations

The report includes the following visualizations specified in the assignment:

Visualization

Chart Type

Purpose

Sales Target Achievement by Category

Clustered Column Chart

Compare actual sales with sales targets across categories

Maximum Profit Margin by Sub-Category

Donut Chart

Compare maximum profit margin across sub-categories

Monthly Sales Trend

Line Chart

Analyze monthly sales trends over time

Profit vs Quantity by Sub-Category

Scatter Chart

Explore the relationship between profit and quantity sold

Total Sales Amount and Target

Card Visuals

Display total sales and total target

Minimum Target by Segment

Multi-row Card

Display minimum target values for relevant segments

Sales Performance Matrix

Matrix

Compare actual sales and targets by category and month

Geographic Sales Analysis

Map

Identify sales distribution across cities

Sales Distribution by Sub-Category

Treemap

Compare sales contribution by sub-category

Order Count Analysis by State

Funnel Chart

Visualize order counts across states

Key Analytical Areas

Sales target achievement and category performance.

Monthly sales growth and trends.

Profitability across product sub-categories.

Quantity sold and its relationship with profit.

Geographic sales distribution.

Order volume across states.

Actual sales versus target performance.
💡 Skills Demonstrated

Data Analysis

DAX Calculated Columns and Measures

Data Modeling

Data Transformation

Sales and Profitability Analysis

Time Intelligence

KPI Reporting

Interactive Data Visualization

Business Intelligence Reporting

GitHub Project Documentation

🚀 Conclusion

This project demonstrates the practical application of Power BI and DAX for analyzing e-commerce business data. By combining data modeling, calculated columns, analytical measures, and interactive visualizations, the report provides a foundation for evaluating sales performance, profitability, target achievement, and regional trends.
