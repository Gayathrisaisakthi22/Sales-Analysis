# Sales-Analysis Dashboard

### Project Overview
This data analysis project aims to provide insights into the sales performance of an company over the past year. By analyzing various aspects of the sales data, we seek to identify trends, make data-driven recommendations, and gain a deeper understanding of the company's performance.

![Pizza Sales Dashboard 1](https://github.com/Gayathrisaisakthi22/Sales-Analysis/assets/159177772/8f24bd62-1d64-462c-83c6-97f5dd43da08)
















![Pizza Sales Dashboard 2](https://github.com/Gayathrisaisakthi22/Sales-Analysis/assets/159177772/ea2c91c4-cb75-480a-b995-f6637c525e15)

### Data Sources
Sales Data: The primary dataset used for this analysis is the "pizzasales_data.csv" file, containing detailed information about each sale made by the company.

### Tool
-  MS Excel - Data Cleaning
- MS SQL Server - Data Analysis
- PowerBI - Creating reports

### Data Cleaning/Preparation
In the initial data preparation phase, we performed the following tasks:

- Data loading and inspection.
- Handling missing values.
- Data cleaning and Power query

### Exploratory Data Analysis
EDA involved exploring the sales data to answer key questions, such as:
- KPIS
- Daily Trend for Total Orders, Monthly Trend for Orders
- % of Sales by Pizza Category, % of Sales by Pizza Size
- Total Pizzas Sold by Pizza Category
- Top 5 Pizzas by Revenue, Bottom 5 Pizzas by Revenue
- Top 5 Pizzas by Quantity, Bottom 5 Pizzas by Quantity
- Top 5 Pizzas by Total Orders, Bottom 5 Pizzas by Total Orders

### Data Analysis

Include some interesting code/features worked with


-- Average Pizzas Per Order
``` sql
SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / 
CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2))
AS Avg_Pizzas_per_order
FROM pizza_sales
```

-- Daily Trend for Total Orders
``` sql
SELECT DATENAME(DW, order_date) AS order_day, COUNT(DISTINCT order_id) AS total_orders 
FROM pizza_sales
GROUP BY DATENAME(DW, order_date)
```

-- Sales by Pizza Category
``` sql
SELECT pizza_category, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
FROM pizza_sales
GROUP BY pizza_category
```

### Results/Findings
--Revenue: 
- The Thai chicken Pizza contributes the maximum Revenue.
  
--Quantity: 
- The Classic Deluxe Pizza Contributes to maximum Total Quantities.
  
--Total Orders: 
- The Classic Deluxe Pizza Contributes to maximum Total Orders.

--Orders are highest on, weekends, Friday / Saturday evenings.

### Recommendations
- Focus on expanding and promoting products in Large size Pizza.
- Invest in marketing and promotions during peak sales seasons to maximize revenue.
  









