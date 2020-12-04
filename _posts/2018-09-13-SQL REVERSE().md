---
bg: "tools.jpg"
layout: post
title:  SQL Function REVERSE()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-09-13
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL REVERSE() function is used for reversing the string. It accepts a string of characters as an argument and returns the reverse order of the string. The REVERSE is one of the [SQL String Functions](https://appdividend.com/2019/08/12/sql-string-functions-example-string-functions-in-sql/), which is used to reverse the specified expression. The REVERSE() function reverses a string and returns the result.

# **SQL REVERSE Function**

The REVERSE function is used to reverse the given string.

See the following syntax of the REVERSE function.

# **Syntax**

```
SELECT REVERSE(string)
```

# **Parameters**

**String:** It is the source string of which characters have to be reversed.

# **Note**

The string expression must be of a data type that can be implicitly converted to **VARCHAR**. Otherwise, **CAST** has to be used explicitly for converting to **VARCHAR**.

# **Example**

See the following query.

```
SELECT REVERSE ('AppDividend.com');

```

### **Output**

```
moc.dendiviDppA

```

# **Query 2**

```
SELECT REVERSE ('edcba');

```

### **Output**

```
abcde

```

# **Query 3**

```
SELECT REVERSE (' SQL');

```

### **Output**

```
LQS
```

# **Query 4**

```
SELECT REVERSE ('123');

```

### **Output**

```
321

```

Above were the common examples to make clear how this function work. Let’s apply this function to a TABLE.

### **Table: Employee**

[Untitled](https://www.notion.so/40e098ce30ba4bdfbe7d6132b899dcf2)

Suppose we want to reverse the first_name of the employee, then the following query has to be considered.

# **Query**

```
Select First_name, REVERSE (First_name) 
AS Reversed_Name 
from Employee;

```

### **Output**

[Untitled](https://www.notion.so/fccc31f2be17422c9402090d26e81ea1)

Here, you can see that the First_name of the employee has been reversed.

# **SQL SERVER Reverse Function**

Let’s use SQL SERVER REVERSE function to check whether a string is a palindrome or not.

A palindrome string is a string whose original and reversed strings are equal.

```
EX: MaM, DaD

```

# **Query**

```
DECLARE 
@input VARCHAR (100) = 'MadaM';
SELECT 
CASE
WHEN @input = REVERSE(@input)
THEN 'Palindrome'
ELSE 'Not Palindrome'
END result;

```

### **Output**

```
Palindrome
```

### **Explanation**

Here, above string MadaM, which was given as input, was a palindrome.

# **MySQL REVERSE() Function**

MySQL REVERSE() function reverses a string and returns the result.

It works from MySQL 4.0.