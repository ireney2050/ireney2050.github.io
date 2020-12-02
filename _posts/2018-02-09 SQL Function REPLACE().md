---
bg: "tools.jpg"
layout: post
title:  SQL Function Replace()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-01-06
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL replace is an inbuilt function that is used for replacing a sequence of characters in a string with another set of characters. For example, it is used for replacing all the occurrences of a substring within a present string taken from another new string.

SQL replace function performs case sensitive replacement in MySQL but in SQL Server it is case-insensitive. It returns [NULL](https://appdividend.com/2019/08/07/sql-null-functions-example-ifnull-isnull-coalesce-nullif/) if any argument is [NULL](https://appdividend.com/2019/08/07/sql-null-functions-example-ifnull-isnull-coalesce-nullif/).

# **SQL replace function**

If you want to search and replace a substring with a new one in a column then SQL replace() function is your solution. For example, change a dead link to a new one, rename an obsolete product to the new name, etc.

SQL provides a very helpful [string function](https://appdividend.com/2019/08/12/sql-string-functions-example-string-functions-in-sql/) called REPLACE that allows you to replace all the occurrences of the substring in the string with a new substring.

The replace function replaces all the occurrences of the [substring](https://appdividend.com/2019/08/30/sql-substring-function-example-substring-in-sql/) within the string, with a new substring.

See the following syntax.

```
REPLACE(string, old_string, new_string)
```

1. **string:** The string will be used for replacing the set of characters by another set of characters.
2. **old_string**: The substring which will be searched in the string.
3. **new_string**: All occurrences of old_string will be replaced with new_string in the string.

The [function](https://appdividend.com/2019/08/12/sql-string-functions-example-string-functions-in-sql/) returns the new string.

# **#Query**

```
SELECT REPLACE(“I Love SQL”, ’I’, ’Everyone’);

```

See the below output.

```
Everyone Love SQL

```

### **#EXPLANATION**

In this example, it is very well clear that **I** was replaced with **Everyone** who replaced **I love SQL** to the desired output as shown above.

# **#Query**

et’s see another example.

```
SELECT REPLACE(“appdivIdend.com”, ‘i’, ‘3’);
```

See the output.

```
appd3vIdend.com

```

### **#EXPLANATION**

Here, in the above example, i was replaced with 3. As mentioned above, It performs a case sensitive replacement.

This will happen only in MySQL; in SQL server it is not case sensitive. We have also used the [SELECT](https://appdividend.com/2019/04/22/sql-select-query-example-sql-select-statement-tutorial/) statement in the above query.

So, in that case, the output would have been **appd3v3dend.com**

# **#Query**

See the following query.

```
SELECT REPLACE(“ABC DEF ABC”, ‘a’, ’B’);

```

See the output.

```
ABC DEF ABC

```

### **#EXPLANATION**

Here there was no replacement because **“a”** was not present in the first string.

# **#Query**

See the following query.

```
SELECT REPLACE('App Dividend.com', ' ', '_');

```

See the output.

```
App_Dividend.com
```

### **#EXPLANATION**

Here, whitespace or blank space is replaced with an underscore.

# **#Query**

See the following query.

```
SELECT REPLACE(‘AppDividend.com’, ‘i’, ‘123’);

```

See the output.

```
AppD123v123end.com

```

### **#EXPLANATION**

Here, in the above example, i was replaced with 123.

Now, from the examples mentioned above, you might have got a clear picture of what SQL replace function does.

Let’s look at a proper example where it is used.

Suppose we have a table named **STUDENT.**

[Untitled](https://www.notion.so/fbbc98d62c5b4f88843e64ced6f95e1c)

Now, if we want to replace the (.) character with (-) character in the phone column. Then we have to use REPLACE function along with the [UPDATE statement](https://appdividend.com/2019/04/28/sql-update-query-example-sql-update-statement-tutorial/).

# **#QUERY**

```
UPDATE STUDENT SET Phone = REPLACE(Phone, '.', '-');

```

See the output.

[Untitled](https://www.notion.so/db41295d20744c56b917d63385d71013)

So, here you can see that (.) character is replaced with (-) character.