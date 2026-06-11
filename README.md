# 📚 Book Store Database Analysis using SQL

## 📌 Project Overview

The **Book Store Database Analysis Project** is a SQL-based data analytics project designed to manage and analyze a bookstore's inventory, customers, and sales transactions.

The project uses a relational database consisting of three interconnected tables:

* Books
* Customers
* Orders

Through SQL queries, the system generates meaningful business insights related to inventory management, sales performance, customer behavior, revenue generation, and genre-wise book sales.

This project demonstrates practical usage of:

* SQL Database Design
* Data Manipulation
* Joins
* Aggregations
* Business Analytics
* Relational Database Management

---

# 🎯 Objectives

* Manage bookstore inventory efficiently.
* Track customer purchases.
* Analyze sales performance.
* Generate revenue insights.
* Monitor stock availability.
* Identify top-selling genres and books.
* Practice SQL queries ranging from basic to advanced.

---

# 🛠️ Technologies Used

| Technology          | Purpose                 |
| ------------------- | ----------------------- |
| SQL (MySQL)         | Database Management     |
| CSV Files           | Data Source             |
| Relational Database | Data Storage & Analysis |

---

# 📂 Database Schema

## Books Table

Stores information about available books.

| Column         | Description            |
| -------------- | ---------------------- |
| Book_ID        | Unique Book Identifier |
| Title          | Book Title             |
| Author         | Author Name            |
| Genre          | Book Category          |
| Published_Year | Year of Publication    |
| Price          | Book Price             |
| Stock          | Available Quantity     |

---

## Customers Table

Stores customer information.

| Column      | Description                |
| ----------- | -------------------------- |
| Customer_ID | Unique Customer Identifier |
| Name        | Customer Name              |
| Email       | Email Address              |
| Phone       | Contact Number             |
| City        | Customer City              |
| Country     | Customer Country           |

---

## Orders Table

Stores purchase transactions.

| Column       | Description               |
| ------------ | ------------------------- |
| Order_ID     | Unique Order Identifier   |
| Customer_ID  | Customer Reference        |
| Book_ID      | Purchased Book Reference  |
| Order_Date   | Purchase Date             |
| Quantity     | Number of Books Purchased |
| Total_Amount | Total Purchase Value      |

---

# 🔗 Relationships

### Customers → Orders

```sql
FOREIGN KEY (Customer_ID)
REFERENCES Customers(Customer_ID)
```

One customer can place multiple orders.

---

### Books → Orders

```sql
FOREIGN KEY (Book_ID)
REFERENCES Books(Book_ID)
```

One book can appear in multiple orders.

---

# 📊 Dataset Statistics

| Table     | Records |
| --------- | ------- |
| Books     | 500     |
| Customers | 500     |
| Orders    | 500     |

---

# 🚀 Features

## 1️⃣ Inventory Management

Analyze available books and stock levels.

### Queries

* Retrieve all books.
* Find books by genre.
* Find books published after a specific year.
* Identify books with lowest stock.
* Find most expensive books.

---

## 2️⃣ Customer Analysis

Analyze customer demographics.

### Queries

* List customers by country.
* Retrieve customer information.
* Analyze customer purchasing activity.

---

## 3️⃣ Sales Analysis

Generate sales performance reports.

### Metrics

* Total Revenue
* Order Volume
* Quantity Sold
* High-Value Orders

### Example Query

```sql
SELECT SUM(Total_Amount) AS Revenue
FROM Orders;
```

---

## 4️⃣ Revenue Analysis

Calculate total business revenue.

### KPI

```text
Total Revenue Generated
```

Helps understand overall sales performance.

---

## 5️⃣ Stock Analysis

Monitor inventory levels.

### Queries

```sql
SELECT SUM(Stock)
FROM Books;
```

```sql
SELECT *
FROM Books
ORDER BY Stock
LIMIT 1;
```

### Insights

* Total Inventory Available
* Low Stock Alerts

---

## 6️⃣ Genre Analysis

Identify popular book categories.

### Query

```sql
SELECT DISTINCT Genre
FROM Books;
```

### Business Benefit

Understand product diversity and customer preferences.

---

## 7️⃣ Order Analysis

Analyze customer purchases.

### Queries

* Orders placed within a date range
* Orders with quantity greater than 1
* High-value orders

Example:

```sql
SELECT *
FROM Orders
WHERE Quantity > 1;
```

---

# 📈 Advanced SQL Analysis

## Genre-Wise Sales Performance

Determine the total number of books sold in each genre.

```sql
SELECT b.Genre,
       SUM(o.Quantity) AS Total_Books_Sold
FROM Orders o
JOIN Books b
ON o.Book_ID = b.Book_ID
GROUP BY b.Genre;
```

### Insights Generated

* Best-selling genres
* Genre demand analysis
* Inventory planning support

---

# 🧠 SQL Concepts Demonstrated

## Database Design

* CREATE TABLE
* ALTER TABLE
* PRIMARY KEY
* FOREIGN KEY

## Filtering

```sql
WHERE
BETWEEN
DISTINCT
```

## Sorting

```sql
ORDER BY
LIMIT
```

## Aggregate Functions

```sql
SUM()
COUNT()
AVG()
MAX()
MIN()
```

## Joins

```sql
INNER JOIN
```

## Grouping

```sql
GROUP BY
```

---

# 📊 Business Questions Solved

### Inventory

* Which books have the lowest stock?
* What is the total inventory available?

### Sales

* How much revenue has the bookstore generated?
* Which orders generated the highest value?

### Customers

* Which countries have customers?
* Which customers purchase more books?

### Products

* Which genres are available?
* Which genres sell the most?

---

# 🎓 Learning Outcomes

Through this project, you will gain experience in:

* Relational Database Design
* SQL Query Writing
* Database Constraints
* Joins and Relationships
* Aggregation Functions
* Business Analytics
* Inventory Management Systems
* Sales Reporting

---

# 🔮 Future Enhancements

Potential improvements include:

* Stored Procedures
* SQL Views
* Triggers
* Customer Purchase History Reports
* Monthly Sales Dashboard
* Top-Selling Books Analysis
* Revenue Trend Analysis
* Power BI Integration

---

# 📜 Conclusion

The Book Store Database Analysis Project demonstrates the practical application of SQL for managing and analyzing a bookstore's operations. By combining inventory tracking, customer management, sales analytics, and relational database concepts, the project provides valuable business insights and strengthens core SQL skills.

⭐ If you found this project useful, consider giving it a star on GitHub!
