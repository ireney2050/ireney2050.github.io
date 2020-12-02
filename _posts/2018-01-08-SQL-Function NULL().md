---
bg: "tools.jpg"
layout: post
title:  SQL Function Null()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-01-08
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL NULL Functions represent any value that is missing. SQL NULL is described as a blank in a table under any column. The NULL value is something different from Zero and Blank Spaces. NULL functions are the functions that are used for the replacement of NULL values.

# **SQL NULL Functions**

We will see these IFNULL(), ISNULL(), COALESCE(), NULLIF functions.

# **#ISNULL()**

The use of the ISNULL() function is used to replace NULL values in SQL Server.

In MySQL, this function is used to test whether an expression is NULL or not. It usually returns Boolean Values.

# **#Syntax**

```
SELECT column(s), ISNULL (column_name, value_to_replace) 
FROM table_name;

```

# **#Parameters**

1. **Column_name: Column which contains NULL values.**
2. **Value_to_replace**: Value to be replaced in that column.
3. **Table_name:** Name of the [table](https://appdividend.com/2019/04/01/sql-create-table-statement-example-create-table-in-sql-tutorial/).

# **#Example**

See the following example.

```
Select SUM(ISNULL(Salary, 50000) 
AS SALARY from Employee;

```

# **#Output**

**SALARY**

---

820000

---

# **#Explanation**

Here in the above query, we have performed the sum of the salary of employees, and as 1st row had NULL values in the SALARY column his value was replaced by the value as mentioned in the above query, and hence the sum is displayed.
