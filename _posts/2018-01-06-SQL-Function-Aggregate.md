---
bg: "tools.jpg"
layout: post
title:  SQL Function Aggregate()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-01-06
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---


SQL aggregate functions are inbuilt functions that are used for performing various operations in data.  Aggregate Functions are used for performing operations on multiple rows of a particular column and result in a single value. An aggregate function allows you to perform the calculation on a set of values to return the single scalar value.

We often use the aggregate functions with the [GROUP BY](https://appdividend.com/2019/05/21/sql-group-by-example-group-by-clause-in-sql-tutorial/) and [HAVING](https://appdividend.com/2019/06/08/sql-having-clause-example-sql-having-tutorial/) clauses of the [SELECT](https://appdividend.com/2019/04/22/sql-select-query-example-sql-select-statement-tutorial/) statement.

Aggregate Functions are:

1. AVG()
2. COUNT()
3. MAX()
4. MIN()
5. SUM()
6. STDDEV()
7. VARIANCE()

Let’s understand all this function with examples.

# **#Avg() in SQL**

The **avg()** function is used to return an average value after the calculation performed in a numeric column.

### **#Syntax**

```
Select avg (column_name) from table_name;
```

Consider the following [table](https://appdividend.com/2019/04/01/sql-create-table-statement-example-create-table-in-sql-tutorial/).

Consider Table**: (Customers)**

[Untitled](https://www.notion.so/57cf1f0e854543118979da7d0408b637)

### **#Query**

```
select avg(amount) from customers;

```

### **#Output**

![https://appdividend.com/wp-content/uploads/2019/06/SQL-Aggregate-Functions-Example.png](https://appdividend.com/wp-content/uploads/2019/06/SQL-Aggregate-Functions-Example.png)

### **#Explanation**

The above query resulted in the average salary of customers in a table customer.

# **#Count() in SQL**

The count() function is used to count a total number of records in a table with a condition or without a condition.

### **#Syntax**

```
Select count(column_name) from table_name;
```

Consider Table**: (CUSTOMERS)**

[Untitled](https://www.notion.so/2ad4b112ce12493b92dc67d336342547)

### **#Query: (Without a condition)**

```
Select count(cust_code) from customers;

```

See the following output.

![https://appdividend.com/wp-content/uploads/2019/06/Count-in-SQL.png](https://appdividend.com/wp-content/uploads/2019/06/Count-in-SQL.png)

### **#Explanation**

The above query resulted in the total number of customers in a table.

### **#Query: (With a condition)**

```
Select count(cust_code) from customers where amount > 10000;

```

### **#Output**

![https://appdividend.com/wp-content/uploads/2019/06/count_where.png](https://appdividend.com/wp-content/uploads/2019/06/count_where.png)

### **#Explanation**

The above query returned the total number of customers whose amount [where](https://appdividend.com/2019/04/10/sql-where-clause-example-sql-where-query-tutorial/) more than 1000.

# **#Max() in SQL**

The max() function is used to return the maximum value in a column.

### **#Syntax**

```
Select max(column_name) from table_name;

```

Consider Table**: (CUSTOMERS)**

[Untitled](https://www.notion.so/d0979d6a030745d0b163907b0d1dc65d)

### **#Query**

```
Select max(amount) from customers;

```

### **#Output**

![https://appdividend.com/wp-content/uploads/2019/06/Max-in-SQL.png](https://appdividend.com/wp-content/uploads/2019/06/Max-in-SQL.png)

### **#Explanation**

The max() function resulted in the max amount present in the customer table.

# **#Min() in SQL**

The min() function is used to return the minimum value in a column.

### **#Syntax**

```
Select MIN(column_name) from table_name;

```

Consider Table**: (CUSTOMERS)**

[Untitled](https://www.notion.so/54a14e618eab405d964dcd7c6e34e283)

### **#Query**

```
Select min(amount) from customers;
```

### **#Output**

![https://appdividend.com/wp-content/uploads/2019/06/Min-in-SQL.png](https://appdividend.com/wp-content/uploads/2019/06/Min-in-SQL.png)

### **#Explanation**

The min() function query resulted in the min amount present in the customer table.

# **#Sum() in SQL**

The sum() function is used to return the submission of all numeric values in a column.

### **#Syntax**

```
Select SUM(column_name) from table_name;

```

Consider Table**: (CUSTOMERS)**

[Untitled](https://www.notion.so/d3f3f57f113746fb824b67c2c11c9334)

### **#Query**

```
Select sum(amount) from customers;

```

### **#Output**

![https://appdividend.com/wp-content/uploads/2019/06/Sum-in-SQL.png](https://appdividend.com/wp-content/uploads/2019/06/Sum-in-SQL.png)

### **#Explanation**

The sum() function query resulted in the total sum of the amount column.

# **#STDDEV() in SQL**

The stddev() function is used to return the standard deviation of a selected column.

### **#Syntax**

```
Select STDDEV(column_name) from table_name;

```

Consider Table**: (CUSTOMERS)**

[Untitled](https://www.notion.so/80e915259ad24a71a72f88a14627f7c2)

### **#Query**

```
Select STDDEV(amount) from customers;

```

### **#Output**

![https://appdividend.com/wp-content/uploads/2019/06/STDDEV-in-SQL.png](https://appdividend.com/wp-content/uploads/2019/06/STDDEV-in-SQL.png)

### **#Explanation**

The STDDEV query resulted in the standard deviation of an amount column.

# **#Variance() in SQL**

The variance() function is used to return the Variance of a selected column.

### **#Syntax**

```
Select VARIANCE(column_name) from table_name;

```

Consider Table**: (CUSTOMERS)**

[Untitled](https://www.notion.so/115f21012e3542bd90ef301644df3042)

### **#Query**

```
Select variance(amount) from customers;

```

### **#Output**

![https://appdividend.com/wp-content/uploads/2019/06/Variance-in-SQL.png](https://appdividend.com/wp-content/uploads/2019/06/Variance-in-SQL.png)

### **#Explanation**

The above query resulted in the variance of the amount column.