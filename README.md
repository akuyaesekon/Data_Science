# SQL Data Analysis Project: Online Store Sales

This project demonstrates the use of SQL for data analysis by examining a fictional online store's sales, customer behavior, and product performance. The dataset consists of four tables: `Customers`, `Products`, `Orders`, and `Order_Items`. 

In this project, we will analyze various business metrics such as total sales per month, best-selling products, top-spending customers, average order value, and customer purchasing frequency.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Dataset Schema](#dataset-schema)
3. [Analysis Tasks](#analysis-tasks)
4. [SQL Queries and Solutions](#sql-queries-and-solutions)
5. [Usage](#usage)
6. [Contributing](#contributing)
7. [License](#license)

## Project Overview

This SQL project is designed to:
- Analyze sales performance over time.
- Identify top-selling products.
- Understand customer purchasing behavior.
- Compute key performance indicators (KPIs) for an online store.

## Dataset Schema

The project uses the following tables:

### 1. Customers Table

| Column         | Data Type   |
|----------------|-------------|
| customer_id    | INT         |
| first_name     | VARCHAR     |
| last_name      | VARCHAR     |
| email          | VARCHAR     |
| signup_date    | DATE        |

### 2. Products Table

| Column         | Data Type   |
|----------------|-------------|
| product_id     | INT         |
| product_name   | VARCHAR     |
| category       | VARCHAR     |
| price          | DECIMAL     |

### 3. Orders Table

| Column         | Data Type   |
|----------------|-------------|
| order_id       | INT         |
| customer_id    | INT         |
| order_date     | DATE        |
| total_amount   | DECIMAL     |

### 4. Order_Items Table

| Column         | Data Type   |
|----------------|-------------|
| order_item_id  | INT         |
| order_id       | INT         |
| product_id     | INT         |
| quantity       | INT         |

## Analysis Tasks

The following analyses are performed on the dataset:

1. **Total Sales per Month**  
   Calculate the total revenue generated each month.

2. **Best-Selling Products**  
   Identify the top-selling products based on quantity sold.

3. **Top 5 Customers by Spending**  
   Identify the top 5 customers based on total spending.

4. **Average Order Value**  
   Calculate the average value of all orders placed.

5. **Customer Purchasing Frequency**  
   Determine the average number of orders placed by each customer.

## SQL Queries and Solutions

### 1. Total Sales per Month

```sql
SELECT 
    DATE_FORMAT(order_date, '%Y-%m') AS month,
    SUM(total_amount) AS total_sales
FROM 
    Orders
GROUP BY 
    month
ORDER BY 
    month;
