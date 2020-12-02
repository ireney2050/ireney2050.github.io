---
bg: "tools.jpg"
layout: post
title:  SQL Function Char()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-03-29
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL CHAR() is an inbuilt function that is used to convert a numeric value to character. It is just the opposite of the [ASCII()](https://appdividend.com/2019/09/16/sql-ascii-function-example-ascii-function-in-sql/) function. A character or string function is a function which takes one or more characters or numbers as parameters and returns the character value.

# **SQL Char Function**

SQL CHAR() function returns the character based on the ASCII code.

See the following syntax.

```
Select CHAR (number_code)

```

# **Number_code**

The number from which character is to be retrieved. An integer outside the range 0 to 255 will return a **NULL** character.

See the following code.

```
SELECT CHAR (97);

```

See the output.

```
a
```

# **Explanation**

As ASCII value of **a** is 97 so character **a** is printed when number 97 was given as an input to the function.

Let’s see the second query.

```
SELECT CHAR (65);
```

See the output.

```
A
```

# **Explanation**

As the ASCII value of **A** is 65, so character **A** is printed when number 65 was given as an input to the function.

# **Range of ASCII values for characters**

```
A-Z: 65-90
a-z: 97-122
```

Let’s apply the ASCII function to a table.

**Table: Employee**

[Untitled](https://www.notion.so/24d4aa3479cd4d04872172590543222a)

Suppose we want to print the Character Code for **Emp_id** of **Emp_Name**, then the following query has to be considered.

See the following query.

```
Select Emp_name, CHAR(Emp_id) AS CharCode 
from Employee;

```

See the output.

[Untitled](https://www.notion.so/7d91b201a2f441a6b82ad52ee237e56a)

So, you can see from the output that the Character Code of Employee Id is returned under the column name CharCode.

SQL CHAR function can also be used as control characters.

[Untitled](https://www.notion.so/101b9891743844cdbee1fc19bec6bcb7)

# **Multiple Integers**

The char() function doesn’t support the multiple integers as arguments.

If you provide multiple integers, you’ll get an error.

See the following code example.

```
SELECT CHAR(67, 255) AS 'Result';
```

See the output.

```
The char function requires 1 argument(s).
```

Note that this is in contrast to MySQL’s **CHAR()** function which allows you to provide multiple integers in the argument.

# **Out of Range Integers**

The function also doesn’t support the integers outside a range of 1 to 255. If your argument is outside that range, the result is **NULL**.

See the following query.

```
SELECT CHAR(256) AS 'Result';
```

See the following output.

```
+----------+
| Result   |
|----------|
| NULL     |
+----------+

```

This is again in contrast to the MySQL’s CHAR() function, which accepts the integers larger than 255 in which case, they’re automatically converted into multiple result bytes.

# **Inserting Control Characters**

See the following code.

```
SELECT 'Homer' + CHAR(13) + 'krunal@appdividend.com' AS 'Name/Email';
```

See the output.

```
+--------------+
| Name/Email   |
|--------------|
| Homer
krunal@appdividend.com              |
+--------------+
```

Here’s what it looks like if we remove the CHAR(13):

```
SELECT 'KRUNAL' AS 'Name', 'krunal@appdividend.com' AS 'Email';
```

See the output.

```
+--------+-----------------------+
| Name   | Email                 |
|--------+-----------------------|
| KRUNAL |krunal@appdividend.com |
+--------+-----------------------+
```
