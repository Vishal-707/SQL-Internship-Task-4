# SQL-Internship-Task-4

This task demonstrates the use of SQL Aggregate functions such as COUNT, SUM, AVG, MAX, and MIN 
in combination with GROUP BY and HAVING to summarize and filter grouped data from a E-commerce database.
present table in database product customer payment order etc.

---

# Learn 

* `GROUP BY` helps summarize data by grouping rows based on common values.
* Aggregate functions (`COUNT`, `SUM`, `AVG`, `MAX`, `MIN`) provide quick statistics for each group.
* `HAVING` allows filtering of groups after aggregation.
* These queries are crucial for reporting and analytics in database-driven applications.

--- 

## Basic SQL Aggregate Function
Aggregate Functions are used to perform calculations on multiple rows of data and return a single result.
These functions are often used with the group by clause to summarize data for groups of rows.

| Function   | Definition                                                       |
| ---------- | ---------------------------------------------------------------- |
| `COUNT()`  | Returns the number of rows.                                      |
| `SUM()`    | Returns the total sum of a numeric column.                       |
| `AVG()`    | Returns the average value of a numeric column.                   |
| `MAX()`    | Returns the highest value in a set.                              |
| `MIN()`    | Returns the lowest value in a set.                               |


---

-- Show how many of customer_id in customers table.

```sql
SELECT COUNT(Customer_id) FROM Customers ;
```

--- 

# GROUP BY 
The GROUP BY statement groups rows that have the same values into summary rows. It collects data from multiple records and groups the result by one or more column.
The GROUP BY statement is often used with aggregate functions COUNT(), MAX(), MIN(), SUM(), AVG() to group the result-set by one or more columns

* Syntax  Without Aggregate Fun... 
```sql
SELECT column_Name FROM table_name GROUP BY column_Name ;
```
  
* Syntax With Aggregate Fun...
```sql
SELECT column1, aggregate_function(column2) FROM table_name GROUP BY column1;
```

-- Ex. Find the total number of Category 
```sql
SELECT Category , COUNT(category) AS Count FROM Products GROUP BY Category ; 
```
---

# HAVING CLAUSE 
The HAVING CLAUSE in SQL is used to filter result from a GROUP BY query based on an aggregate condition.
It allows you to specify condition for groups (or Aggregates) unlike the WHERE clause which filters rows before grouping.

* Syntax
```sql
SELECT column_name, aggregate_function(column_name) FROM table_name WHERE condition GROUP BY column_name HAVING aggregate_condition ORDER BY column_name ;
```

-- Ex. Which payment types have been used for a total revenue exceeding 2,00,000 ? List the payment 
type and its total revenue. 

```sql
SELECT Payment_Type, SUM(Amount) AS Total_Revenue FROM Orders 
GROUP BY Payment_Type HAVING Total_Revenue > 200000 ;
```
---






  




