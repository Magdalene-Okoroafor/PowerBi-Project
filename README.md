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

- Fact Table: Sales Table, Inventory
- Dimension Tables: Products, Stores, and Dates

### DAX 

1. Date 

Table

<pre>
   Date_Table = CALENDARAUTO()
</pre>
 
 2. Inventory 

Column

<pre>
   Inventory Value = Inventory[Stock_On_Hand]*RELATED(Products[Product_Cost])
</pre>

3. Products

Measure

<pre>
   No of Products = COUNTROWS(Products)
</pre>

<pre>
  Profit Category = SUMX(VALUES(Products[Product_Category]), [Total Profit])
</pre>

<pre>
  Sales Category = CALCULATE([Total Sales], ALL(Products[Product_Category]))
</pre>

4.  Sales 

Measure

<pre>
  Total Cost = SUMX (Sales,Sales[Units]*RELATED(Products[Product_Cost]))
</pre>

<pre>
  Total Profit = [Total Sales]-[Total Cost]
</pre>

<pre>
  Total Sales = SUMX(Sales,Sales[Units]*RELATED(Products[Product_Price]))
</pre>

<pre>
  Total Units Sold = SUM(Sales[Units])
</pre>


4.  Stores

Measure

<pre>
  No of Stores = COUNTROWS(Stores)
</pre>

<pre>
  Profit by Store = CALCULATE([Total Profit],VALUES(Stores[Store_Location]))
</pre>


### Results

Summary of Key Insights from the Maven Toy Analysis:

This analysis evaluates sales and inventory data from Maven Toy Store, a toy retail chain in Mexico. Using Microsoft Power BI, key insights were derived on product profitability, store performance, seasonal trends, and inventory management. 

Findings revealed that Toys and Electronics drive the highest profits, with Downtown stores performing best. Sales peak between March and July, while October sees the lowest revenue. Inventory analysis indicates stock will last 15-17 days.

Recommendations include optimizing inventory, investing in high-performing locations, andaddressing seasonal sales fluctuations to enhance profitability and business growth.


<img width="853" height="476" alt="Maven Toy Shop Dashboard" src="https://github.com/user-attachments/assets/37d4d293-2522-476a-a120-24377df0ec66" />



### Key Insights and Recommendations

###Product Analysis

📓 Which product categories generate the highest profits?
• Toys are the most profitable, contributing $1.08M (26.89%) of total profits.
• Electronics follow closely with $1M (25%).
• Sports & Outdoor products generate the lowest profit at $500K.


📓 Are these profit trends location-dependent?
• Electronics dominate in Airport and Commercial locations.
• Toys perform best in Downtown and Residential areas.

Top Performing Products
Highest Profit-Generating Products:
1. Colorbuds - $835K
2. Action Figure - $348K
3. Lego Bricks - $298K
4. Deck of Cards - $252K
5. Glass Marbles - $190K
   
Most Sold Products:
1. Colorbuds - 104K units (23.5%)
2. Playdoh Can - 103K units (23.2%)
3. Barrel O’Slime - 91K units
4. Deck of Cards - 84K units
5. Magic Sand - 61K units
   
• Notably, Playdoh Can ranks high in sales volume but not in profitability.

### Store & Location Analysis

📓 Which locations generate the highest profits?
• Downtown stores lead with over $2M in profits.
• Airport stores yield the lowest profit at $378K.

Most Profitable Stores:
1. Maven Toys Ciudad de Mexico 2 - $170K
2. Maven Toys Guadalajara 3 - $121K
3. Maven Toys Ciudad de Mexico 1 - $111K
4. Maven Toys Monterrey 2 - $107K
5. Maven Toys Toluca - $105K
   
Least Profitable Stores:
• Maven Toys Cuernavaca 1 - $57K
• Maven Toys La Paz 1 - $57K

### Seasonal Trends & Patterns
• Peak Sales & Profits: March–July
o Highest Sales: April (112K units)
o Highest Profit: March ($406K)

• Lowest Sales & Profits: October
o Sales: 48K units
o Profit: $179K
• Quarterly Trends:
o Q2 (April–June): Highest sales
o Q4 (October–December): Lowest sales

Yearly Trends:
• 2017: Sales peaked towards year-end.
• 2018: Stronger sales from February–July, with March leading.

### Inventory Analysis
Current Inventory Value & Turnover:
• Total Inventory Value: $300K
• Total Stock: 29,742 units
• Average Daily Sales: 1,709 units
• Estimated Inventory Duration: 15-17 days before restocking is required.

### Summary & Recommendations
Summary of Key Findings:
1. Downtown stores are the most profitable.
2. Toys lead in profitability, followed by Electronics.
3. Sales dip in January, February, and October.
4. Electronics excel in Airport and Commercial locations, while Toys dominate Downtown
and Residential areas.

Strategic Recommendations:
1. Expand investment in Downtown stores to capitalize on high profitability.
2. Investigate low sales in January and February to identify and mitigate potential market
challenges.
3. Enhance inventory management to avoid stock shortages or excesses, ensuring optimal
stock levels.


   


