# 📚 Online Bookstore SQL Analysis

## 📌 Project Overview
This project analyzes an online bookstore database using SQL to extract business insights related to sales, customers, and inventory.

## 🗂️ Dataset
The database consists of 3 tables:
- Books (Book_ID, Title, Author, Genre, Price, Stock, Published_Year)
- Customers (Customer_ID, Name, City, Country)
- Orders (Order_ID, Customer_ID, Book_ID, Quantity, Total_Amount, Order_Date)

## 🎯 Objectives
- Analyze book sales and revenue
- Identify top-performing books and genres
- Understand customer purchasing behavior
- Track inventory and stock movement

## 🛠️ SQL Concepts Used
- Joins (INNER JOIN)
- Aggregations (SUM, AVG, COUNT)
- Group By & Having
- Filtering (WHERE, BETWEEN)
- Sorting (ORDER BY)
- Data Cleaning (COALESCE)

## 📊 Key Business Insights
- Identified top-selling genres based on quantity sold
- Found highest revenue-generating customers
- Determined most frequently ordered books
- Analyzed stock consumption vs remaining inventory

## 🚀 Sample Queries

### Total Revenue
SELECT ROUND(SUM(total_amount),0)
FROM orders;

### Top Customers by Spend
SELECT c.Name, ROUND(SUM(o.Total_Amount),0) AS Total_Spent
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
GROUP BY c.Name
ORDER BY Total_Spent DESC;
