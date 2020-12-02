---
bg: "tools.jpg"
layout: post
title:  SQL Function Contact()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-01-06
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

S**QL** **CONCAT** function is used to concatenate two strings to form a single string. SQL CONCAT function is used to join two or more strings. It takes up to 255 input strings which are further joined by the function. For, performing join operation CONCAT requires at least 2 strings. If it is provided with only one string, it will raise an error.

# **SQL CONCAT Function**

If any non-character string values are passed in the function, it will be implicitly converted to strings before concatenating. If any NULL is added to the function, it converts it into an empty string with VARCHAR (1).

# **Syntax**

```
SELECT CONCAT (string1, string2, ... string_n)

```

# **Parameters**

**CONCAT:** This is the function that is used for concatenating.

**string1, string2, … string_n: These are the strings that are used for concatenating.**

See the following query.

```
Select concat (‘Appdividend’, ‘.com’);

```

See the output.

```
Appdividend.com

```

See the query.

```
Select concat (‘App’, ‘Div’, ‘idend’, ‘.com’);

```

See the output.

```
Appdividend.com

```

See the following query.

```
Select concat ('Love', ' ', 'is', ' ', 'Life');

```

See the output.

```
Love is Life

```

Here we used space as another character to concatenate with the words. Adding space prevents our values from being squished together.

See the following query.

```
SELECT CONCAT ('Let', '''', 's learn MySQL');
```

See the output.

```
Let's learn MySQL
```

In the above example, we have used the second parameter within the CONCAT function to add a single quote into the middle of the resulting string.

Above were the common examples to make clear how concat function works.

Let’s see the example with proper tables.

Consider table **Employee**

[Untitled](https://www.notion.so/123c5e757a7b404f9dafbb599fceb75f)

Now suppose we want to concatenate **first_name** and **last_name** under the single column name **Emp_name** then the following query has to be used.

See the following query.

```
Select Concat (First_name, ' ', Last_name) AS Emp_name 
from Employee;
```

See the output.

[Untitled](https://www.notion.so/af84c309c7564e74adf289657319e3a4)

Here you can see that names were concatenated under a single column name **Emp_name**. Here we have also used Space as an additional character to add space between two names to avoid confusion between the name.