📊 Retail Sales Data Analysis Project
📌 Project Overview

This project focuses on analyzing retail transaction data using SQL to extract meaningful business insights. The goal is to understand sales performance, customer behavior, and product trends.

🎯 Objectives
Analyze total sales across different regions
Identify top-performing products
Track monthly sales trends
Compare online vs offline sales
Understand customer purchasing behavior
🛠️ Tools & Technologies
SQL (MySQL / PostgreSQL / SQLite)
Database: retailtransactions_120
Power BI (for visualization – optional)
📂 Dataset Description

The dataset contains retail transaction records with the following fields:

TransactionID
CustomerID
ProductName
Region
Date
SalesChannel (Online/Offline)
TotalAmount
📊 Business Queries & Insights
1️⃣ Total Sales per Region
SELECT 
    Region,
    SUM(TotalAmount) AS Total_Sales
FROM retailtransactions_120
GROUP BY Region
ORDER BY Total_Sales DESC;
2️⃣ Top 5 Best-Selling Products
SELECT 
    ProductName,
    SUM(TotalAmount) AS Revenue
FROM retailtransactions_120
GROUP BY ProductName
ORDER BY Revenue DESC
LIMIT 5;
3️⃣ Monthly Sales Trend
SELECT 
    MONTH(Date) AS Month,
    SUM(TotalAmount) AS Total_Sales
FROM retailtransactions_120
GROUP BY Month
ORDER BY Month;
4️⃣ Region-wise Sales Contribution (%)
SELECT 
    Region,
    SUM(TotalAmount) AS Sales,
    ROUND(
        (SUM(TotalAmount) / (SELECT SUM(TotalAmount) FROM retailtransactions_120)) * 100, 2
    ) AS Contribution_Percentage
FROM retailtransactions_120
GROUP BY Region;
5️⃣ Online vs Offline Sales Comparison
SELECT 
    MONTH(Date) AS Month,
    SalesChannel,
    SUM(TotalAmount) AS Sales
FROM retailtransactions_120
GROUP BY Month, SalesChannel
ORDER BY Month, SalesChannel;
6️⃣ Customer Purchase Frequency
SELECT 
    CustomerID,
    COUNT(TransactionID) AS Purchase_Count
FROM retailtransactions_120
GROUP BY CustomerID
ORDER BY Purchase_Count DESC;
7️⃣ Customers with High Purchases
SELECT 
    CustomerID,
    COUNT(TransactionID) AS Purchase_Count
FROM retailtransactions_120
GROUP BY CustomerID
HAVING COUNT(TransactionID) > 10;
📈 Key Insights
Identify high-revenue regions for business expansion
Focus on top-selling products for marketing strategies
Understand seasonal sales patterns
Analyze customer loyalty and repeat purchases
Compare performance of sales channels
🚀 How to Use
Import dataset into your SQL database
Run the queries provided in this project
Analyze the output results
(Optional) Connect to Power BI for visualization
📌 Future Improvements
Add predictive analysis (sales forecasting)
Build dashboards in Power BI
Perform customer segmentation
Include advanced KPIs

---dashboard---
<img width="1307" height="729" alt="image" src="https://github.com/user-attachments/assets/4e963533-4ac8-4c09-9924-80995d797d67" />


