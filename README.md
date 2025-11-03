# E-Commerce Analytics & Data Warehouse | MySQL + Python

This project demonstrates the end-to-end development of a relational data warehouse using **MySQL** along with **Python (Pandas + MySQL Connector)** for data extraction, transformation, and loading (ETL).  
Analytical SQL queries are performed to uncover valuable business insights such as revenue trends, customer behavior, and product performance.


## 🎯 Project Objectives

- Design and build a structured e-commerce data warehouse
- Automate table creation and data loading from multiple CSV sources
- Enable advanced SQL analytics for business intelligence
- Ensure clean, consistent, and relational data modeling


## 🧱 Architecture & Tools

| Component | Technology |
|----------|------------|
| Programming Language | Python |
| Database | MySQL |
| Libraries | Pandas, MySQL-connector-python |
| Visualization (Optional) | Matplotlib, Seaborn |
| Environment | Jupyter Notebook / MySQL Workbench |


## 📂 Data Source

Dataset includes 7 raw CSV files representing different business entities:

| CSV File | SQL Table | Description |
|--------|----------|-------------|
| customers.csv | customers | Customer demographic details |
| orders.csv | orders | Purchase records & statuses |
| sellers.csv | sellers | Marketplace sellers |
| products.csv | products | Product catalogue |
| geolocation.csv | geolocation | Zip code & city mapping |
| payments.csv | payments | Order payment information |
| order_items.csv | order_items | SKU per order & pricing |

## 🔄 ETL Workflow

✅ Import datasets using Pandas  
✅ Clean and standardize missing or incorrect entries  
✅ Auto-detect SQL data types  
✅ Dynamically create MySQL tables  
✅ Bulk insert all dataset records  
✅ Validate table relationships with SQL joins  

This ensures structured, query-friendly data optimized for analytics.

## 📊 Business Insights & SQL Queries

A few example insights generated:

### ✅ Total revenue by product category
```sql
SELECT p.product_category, 
       ROUND(SUM(oi.price), 2) AS total_revenue
FROM products p
JOIN order_items oi ON p.product_id = oi.product_id
GROUP BY p.product_category
ORDER BY total_revenue DESC;
