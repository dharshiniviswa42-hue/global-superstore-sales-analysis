#  Global Superstore Sales Analysis

##  Project Overview
Sales analysis of Global Superstore dataset (51K rows) 
using SQL, Excel and Power BI. The goal was to identify 
top performing regions, categories, customer segments 
and loss making products.

##  Tools Used
- **Excel** — Data Cleaning
- **SQL (MySQL)** — Data Analysis
- **Power BI** — Dashboard & Visualization

##  Dataset 
- File: sales analysis project.csv 
- Description: Cleaned dataset after removing duplicates, handling null values, and correcting data types  
- Source: Kaggle - Superstore Sales Dataset  
- Author: Aditi Saxena
- 51,290 rows | 21 columns
- Years: 2011–2014
- Global sales data across 13 regions

##  SQL Queries & Analysis

### Q1: Sales & Profit by Region
```sql
SELECT region,
ROUND(SUM(sales),2) AS total_sales,
ROUND(SUM(profit),2) AS total_profit
FROM sales_project
GROUP BY region
ORDER BY total_sales DESC;
```
**Finding:** Central region leads with $2.8M sales

![Q1 Result](1.sql%20pro.png)

---

### Q2: Sales by Category
```sql
SELECT category,
ROUND(SUM(sales),2) AS total_sales
FROM sales_project
GROUP BY category
ORDER BY total_sales DESC;
```
**Finding:** Technology is top category at $4.7M

![Q2 Result](2.sql%20pro.png)

---

### Q3: Sales by Year
```sql
SELECT year,
ROUND(SUM(sales),2) AS total_sales
FROM sales_project
GROUP BY year
ORDER BY total_sales DESC;
```
**Finding:** Sales grew 90% from 2011 to 2014

![Q3 Result](3.sql%20pro.png)

---

### Q4: Profit by Segment
```sql
SELECT segment,
ROUND(SUM(profit),2) AS total_profit
FROM sales_project
GROUP BY segment
ORDER BY total_profit DESC;
```
**Finding:** Consumer segment most profitable at $749K

![Q4 Result](4.sql%20pro.png)

---

### Q5: Loss Making Products
```sql
SELECT product_name,
ROUND(SUM(profit),2) AS total_profit
FROM sales_project
WHERE profit < 0
GROUP BY product_name
ORDER BY total_profit ASC
LIMIT 10;
```
**Finding:** Cubify 3D Printer biggest loss at -$9,240

![Q5 Result](5.sql%20pro.png)

---

##  Key Findings
1. Central region has highest sales ($2.8M)
2. Technology is top selling category ($4.7M)
3. Sales grew 90% from 2011 to 2014
4. Consumer segment most profitable ($749K)
5. Cubify 3D Printer biggest loss maker (-$9,240)

##  Dashboard
![Dashboard](superstore-dashboard.png)

##  Conclusion
This analysis reveals that the Central region and 
Technology category drive the most revenue. Consumer 
segment is the most profitable customer group. Sales 
showed consistent 90% growth from 2011 to 2014. 
However, certain products like Cubify 3D Printer and 
Smart Phones are generating significant losses and 
require immediate pricing strategy review.
````


