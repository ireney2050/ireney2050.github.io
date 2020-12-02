---
bg: "tools.jpg"
layout: post
title:  SQL Function Substring()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-03-18
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL Substring is an inbuilt function that is used to extract the part of a string from an original string given as an input to the function. Part of the string is known as a substring. The SUBSTRING functions allow you to extract a substring from a string.

# **SQL Substring Function**

SQL SUBSTRING() method allows us to obtain the substring from the main string. If there is some use case like you want to check the part of the output string then you can use the substring() function.

See the syntax of the Substring function.

```
SELECT SUBSTRING (input_string, start_position, length);

```

See the following parameters.

1. **input_string:** The source string from which substring will be extracted. It can be a character, binary, text, or image expression.
2. **start_position:** It is an integer that specifies the location where the returned substring starts. The first character in an input_string is 1, not zero as that of in C or C++.
3. **Length:** It is a positive integer that specifies the number of characters to be extracted. The function will raise an error if the length is negative.

If the start + length > the length of input_string, a substring will begin at the start and will include the remaining characters of the input_string.

See the following example.

```
Select substring ('AppDividend.com', 1, 5);

```

See the output.

```
AppDi
```

Here, the start position was one, so it started from **A** and ended at **I** because the requirement was length 5.

### **Example 2**

See the following query.

```
Select substring ('AppDividend.com', 4, 8);
```

See the output.

```
Dividend
```

Here, the start position was from 4, so it started from **D** and ended at **d** because the requirement was length 8.

### **Example 3**

See the following query.

```
Select substring ('AppDividend.com', -12, 8);

```

See the output.

```
Dividend
```

Here the start position was from -12 so it started from **D** and ended at **d** because the requirement was length 8.

### **Note:**

An index of the last character is -1, followed by -2 and so on. The previous example -12 was there, so it started from **D** if it was -1 then it would have started from **m** and ended at **m** because there is no further string after that.

So, the output would have been the only m.

Above were all the typical examples to make you clear how substring function works.

Let’s see the example with proper tables.

### **Table: Employee**

[Untitled](https://www.notion.so/66bceee3db4a4b599e50f34cccd8d135)

Now suppose we want to extract only the first name from emp_name then the following query has to be taken.

See the query.

```
SELECT SUBSTRING (Emp_name, 1, 5) AS First_name
FROM Employee;

```

See the output.

**Emp_name**

---

Rohit

---

Shiva

---

Karan

---

Suraj

---

Akash

---

Here, you can see that only **first_name** is displayed which was extracted from **Emp_name**.

In MySQL, The SUBSTR() and MID() functions equals to the SUBSTRING() function.

# **Applications**

1. Simple data handling with the SQL Server Substring function.
2. Use of the SQL Server SUBSTRING function in the where clause.
3. Dynamically locate the starting and end character.
4. Working with DateTime strings.
5. Creating a simple sub-select.

So, we have seen several examples of the SUBSTRING function in SQL Server, the character functions that SQL server makes readily available for use, and how you can use them to manipulate string values in your database and your result set.
