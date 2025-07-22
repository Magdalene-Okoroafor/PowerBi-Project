# Maven Toy Store Analysis

### Introduction

This business intelligence (BI) analysis focuses on Maven Toy Store, a leading toy retail chain in Mexico. The dataset encompasses extensive sales and inventory data, including product details, store locations, daily sales transactions, and stock levels across multiple outlets.

### Project Overview

As a BI consultant recently engaged by Maven Toys, the role is to uncover significant trends and patterns within their data. This analysis aims to support the company's expansion strategy by providing actionable insights for informed decision-making.

### Deliverable

A Power BI dashboard or report featuring data-driven insights and strategic recommendations.

### Dataset Overview

The dataset comprises four core tables:

1. Sales Table: Contains 829,262 unique sales transactions recorded from January 2017 to September 2018.
2. Inventory Table: Provides details of stock availability at each store.
3. Stores Table: Includes data on 50 toy stores across 29 cities in Mexico.
4. Products Table: Lists product IDs, names, costs, and selling prices.


### Objectives of the Analysis

The primary goal of this analysis is to generate actionable insights into Maven Toy Store's overall sales performance and profitability by evaluating:

1. Store location performance
2. Seasonal sales trends
3. Product profitability and sales effectiveness
   
Based on these findings, recommendations will be provided to optimize business strategies.

### Key Business Questions

1. Which product categories yield the highest profits, and how do these trends vary across different store locations?
2. Are there identifiable seasonal sales patterns?
3. What is the company's current market reach in terms of store distribution and geographic presence?
4. What is the total inventory value, and how long can it sustain current sales levels?
5. Which stores perform best and worst in terms of revenue and profitability?

### Tools and Methodologies

Tool Used: Microsoft Power BI

The following BI techniques and concepts were applied:

- Data Cleaning & Transformation using Power Query
- Data Modeling to establish structured relationships between tables
- DAX Implementation for advanced calculations and metrics
- Data Visualization for interactive and insightful dashboards
- Comprehensive Project Documentation for clear reporting of insights


### Data Modeling

Effective data modeling structures raw data into an analytical framework, allowing seamless relationship-building between tables. In this project, Power BI automatically identified table
relationships, forming a star schema model:

• Fact Table: Sales Table, Inventory
• Dimension Tables: Products, Stores, and Dates

### DAX 

1. Auto Calender

<pre>
   Date_Table = CALENDARAUTO()
</pre>
 
 2. Inventory Value

<pre>
   Inventory Value = Inventory[Stock_On_Hand]*RELATED(Products[Product_Cost])
</pre>


   


