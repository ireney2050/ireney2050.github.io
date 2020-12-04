---
bg: "tools.jpg"
layout: post
title:  SQL FORMAT()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-09-23
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL FORMAT() is an inbuilt function that is used for formatting a value with the specified format. The FORMAT() function is used with date/time values and number values. SQL FORMAT() function formats the value with the specified format (and an optional culture in SQL Server 2017). Use the FORMAT() function to format date/time values and number values.

# **SQL Format Function**

SQL Format a value formatted with the specified format and optional culture. Use the FORMAT function for locale-aware formatting of date/time and number values as strings. For general data type conversions, use CAST or CONVERT.

# **Syntax**

```
SELECT FORMAT (value, format, culture);

```

# **Parameters:**

1. **Value: Expression which is to be formatted.**
2. **Format:** The pattern in which expression has to be formatted.
3. **Culture:** It is entirely optional; it specifies the culture.

See the following example.

```
DECLARE @d DATETIME = '28/10/2019';  
SELECT FORMAT (@d, 'd', 'en-US') AS 'US English Result',  
       FORMAT (@d, 'd', 'no') AS 'Norwegian Result',  
       FORMAT (@d, 'd', 'zu') AS 'Zulu Result',
       FORMAT ( @d, 'd', 'en-gb' ) AS 'Great Britain English Result',
       FORMAT ( @d, 'd', 'de-de' ) AS 'German Result',  
       FORMAT ( @d, 'd', 'zh-cn' ) AS 'Simplified Chinese (PRC) Result';
```

See the output.

![https://appdividend.com/wp-content/uploads/2019/11/SQL-Format-Function.png](https://appdividend.com/wp-content/uploads/2019/11/SQL-Format-Function.png)

# **Example 2:**

See the following code.

```
DECLARE @d DATETIME = '10/28/2019';  
SELECT FORMAT ( @d, 'D', 'en-US' ) AS 'US English Result'  
      ,FORMAT ( @d, 'D', 'en-gb' ) AS 'Great Britain English Result'  
      ,FORMAT ( @d, 'D', 'de-de' ) AS 'German Result'  
      ,FORMAT ( @d, 'D', 'zh-cn' ) AS 'Chinese (Simplified PRC) Result';

```

See the output.

![https://appdividend.com/wp-content/uploads/2019/11/How-To-Format-Function-In-SQL.png](https://appdividend.com/wp-content/uploads/2019/11/How-To-Format-Function-In-SQL.png)

**Let’s see the custom format types.**

```
DECLARE @d DATETIME = GETDATE();  
SELECT FORMAT( @d, 'dd/MM/yyyy', 'en-US' ) AS 'DateTime Result'  
       ,FORMAT(123456789,'###-##-####') AS 'Custom Number Result';
```

See the output.

![https://appdividend.com/wp-content/uploads/2019/11/Format.png](https://appdividend.com/wp-content/uploads/2019/11/Format.png)

# **#SQL Format Date Example**

In this example, we first declared a Datetime variable and assigned [GETDATE()](https://appdividend.com/2019/06/16/sql-date-functions-tutorial-with-example-date-and-time-in-sql/) to it. Here, we are going to use the Format function to return the date in different formats.

See the following code example.

```
DECLARE @Vardate DATETIME = GETDATE() 
SELECT FORMAT(@Vardate, 'd', 'en-US' ) AS 'Result 1',  FORMAT(@Vardate, 'D', 'en-US' ) AS 'Result 2'
SELECT FORMAT(@Vardate, 'f', 'en-US' ) AS 'Result 3',  FORMAT(@Vardate, 'F', 'en-US' ) AS 'Result 4'
SELECT FORMAT(@Vardate, 'g', 'en-US' ) AS 'Result 5',  FORMAT(@Vardate, 'G', 'en-US' ) AS 'Result 6'
SELECT FORMAT(@Vardate, 'm', 'en-US' ) AS 'Result 7',  FORMAT(@Vardate, 'M', 'en-US' ) AS 'Result 8'
SELECT FORMAT(@Vardate, 'O', 'en-US' ) AS 'Result 9',  FORMAT(@Vardate, 'R', 'en-US' ) AS 'Result 10'
SELECT FORMAT(@Vardate, 's', 'en-US' ) AS 'Result 11', FORMAT(@Vardate, 'S', 'en-US' ) AS 'Result 12'
SELECT FORMAT(@Vardate, 't', 'en-US' ) AS 'Result 13', FORMAT(@Vardate, 'T', 'en-US' ) AS 'Result 14'
SELECT FORMAT(@Vardate, 'u', 'en-US' ) AS 'Result 15', FORMAT(@Vardate, 'U', 'en-US' ) AS 'Result 16'
SELECT FORMAT(@Vardate, 'Y', 'en-US' ) AS 'Result 17'
```

See the output.

![https://appdividend.com/wp-content/uploads/2019/11/SQL-Format-Date-Example.png](https://appdividend.com/wp-content/uploads/2019/11/SQL-Format-Date-Example.png)

# **#SQL Format Date using Culture**

In this example, we are going to use the format function third argument culture.

By this, you can display the month name, or day name in the native language — something like, Day name in J Hindi, Russian, Korean, Japanese, Chineses, etc.

See the following query.

```
DECLARE @Vardate DATETIME = GETDATE() 
SELECT FORMAT(@Vardate, 'dd', 'en-US' ) AS 'Result 1',  FORMAT(@Vardate, 'dddd', 'hi-IN' ) AS 'Result 2'
SELECT FORMAT(@Vardate, 'd', 'de-DE' ) AS 'Result 3',  FORMAT(@Vardate, 'dddd', 'ru-RU' ) AS 'Result 4'
SELECT FORMAT(@Vardate, 'M', 'en-US' ) AS 'Result 5',  FORMAT(@Vardate, 'MMMM', 'hi-IN' ) AS 'Result 6'
SELECT FORMAT(@Vardate, 'MM', 'de-DE' ) AS 'Result 7',  FORMAT(@Vardate, 'MMMM', 'ru-RU' ) AS 'Result 8'
SELECT FORMAT(@Vardate, 'yy', 'en-US' ) AS 'Result 9',  FORMAT(@Vardate, 'y', 'hi-IN' ) AS 'Result 10'
SELECT FORMAT(@Vardate, 'yyyy', 'de-DE' ) AS 'Result 11',  FORMAT(@Vardate, 'y', 'ru-RU' ) AS 'Result 12'
```

See the output.

![https://appdividend.com/wp-content/uploads/2019/11/SQL-Format-Date-using-Culture.png](https://appdividend.com/wp-content/uploads/2019/11/SQL-Format-Date-using-Culture.png)

# **#SQL Server Format Currency using Culture**

In this example, we are going to format the Currency values based on the specified culture.

```
DECLARE @Sales INT = 1111 
SELECT FORMAT(@Sales, 'c', 'en-US' ) AS 'USA Currency'
SELECT FORMAT(@Sales, 'c', 'ru-RU' ) AS 'Russian Currency'
SELECT FORMAT(@Sales, 'c', 'hi-IN' ) AS 'Indian Currency'
SELECT FORMAT(@Sales, 'c', 'de-DE' ) AS 'Indian Currency'
```

See the output.

![https://appdividend.com/wp-content/uploads/2019/11/SQL-Server-Format-Currency-using-Culture.png](https://appdividend.com/wp-content/uploads/2019/11/SQL-Server-Format-Currency-using-Culture.png)