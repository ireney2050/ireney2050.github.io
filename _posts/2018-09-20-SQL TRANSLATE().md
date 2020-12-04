---
bg: "tools.jpg"
layout: post
title:  SQL Funtion TRANSLATE()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-09-20
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL TRANSLATE function is used for replacing the sequence of characters with another set of characters one by one. The TRANSLATE() function returns a string from the 1st argument after the characters specified in the 2nd argument are translated into the characters specified in a third argument.

# **SQL Translate Function**

SQL Server TRANSLATE() function is used to replace several single-characters, one-to-one translation in one operation.

# **Syntax**

```
SELECT TRANSLATE (String, String_to_replace, Replacement_String);

```

# **Parameters**

1. **String:** The Source string where changes have to be made.
2. **String_to_replace: The combination of characters that have to be replaced from the source string.**
3. **Replacement_String:** The Combination of characters which will be used for replacing characters from String_to_replace.

The Function will replace the 1st character in the **string_to_replace** with the first character in the **Replacement_string**.

Then it will replace the second character in the **string_to_replace** with the second character in the **Replacement_string**, and this goes on till the end of the string.

**NOTE:**

1. If the lengths of the String_to_replace and Replacement_string are different, then it will return an error.
2. If any argument is declared [NULL](https://appdividend.com/2019/08/07/sql-null-functions-example-ifnull-isnull-coalesce-nullif/), then the function will return [NULL](https://appdividend.com/2019/08/07/sql-null-functions-example-ifnull-isnull-coalesce-nullif/).

# **Example 1:**

```
SELECT TRANSLATE ('AppDiviDenD', 'ADi', 'adI');

```

### **Output**

```
'appdIvIdend'

```

# **Query 2**

```
SELECT TRANSLATE ('222App', '2A', '3i');

```

### **Output**

```
'333ipp'

```

# **Query 3**

```
SELECT TRANSLATE ('[408] 555 6789', '[]', '()');

```

### **Output**

```
(408) 555 6789
```

Let’s Apply this function in a Table.

# **Table: Employee**

[Untitled](https://www.notion.so/e177af380ae441a3b4123a595e9a79c9)

Suppose, we want to replace ‘abcdefghijk’ with ‘@#$%^&*()}]’ characters just for fun than the following query has to be written.

# **Query**

```
SELECT TRANSLATE (Emp_name,'abcdefghijk', '@#$%^&*()}]’)
FROM Employee;
```

### **Output**

**Emp_name**

---

Ro()t

---

S()v@m

---

K@r@n

---

Sur@}

---

A]@s(

---

Here, you can see the all the string having characters ‘abcdefghijk’ had replaced by ‘@#$%^&*()}]’.

# **SQL TRANSLATE() vs. SQL REPLACE()**

The behavior of the TRANSLATE() function is similar to calling the multiple [REPLACE(](https://appdividend.com/2019/08/25/sql-replace-function-example-replace-function-in-sql/)) functions.

However, the TRANSLATE() function does not replace all the occurrences of the character with a new one.

It is the difference between the TRANSLATE() function and calling multiple [REPLACE()](https://appdividend.com/2019/08/25/sql-replace-function-example-replace-function-in-sql/) functions, and each REPLACE() function call would replace all the relevant characters.

In this tutorial, you have learned how to use the SQL Server TRANSLATE() function to replace the several single-character, one-to-one translation in one operation.

# **Oracle / PLSQL: TRANSLATE Function**

The Oracle/PLSQL TRANSLATE function replaces the sequence of characters in the string with another set of characters.

However, it replaces a single character at a time.

For example, it will replace the first character in the string_to_replace with the first character in the replacement_string. Then it will replace the second character in the string_to_replace with the second character in the replacement_string, and so on.