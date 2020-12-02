---
bg: "tools.jpg"
layout: post
title:  SQL Function Charindex()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-04-02
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---
SQL CHARINDEX is an inbuilt function that is used for returning the location of a substring of a given string. SQL CHARINDEX function is not case-sensitive. SQL CHARINDEX function searches for a substring inside a string starting from a specified location.

It returns the position of the substring found in the searched string, or zero if the substring is not found. The starting position returned is 1-based, not 0-based.

# **SQL CHARINDEX Function**

SQL CHARINDEX() function searches for a substring in a string and returns the position. If the substring is not found, this function returns 0. The function performs a case-insensitive search.

See the following syntax.

```
SELECT CHARINDEX (substring, input_string, [start_position] )

```

# **PARAMETERS**

1. Substring: The substring that you want to find within the input_string.
2. Input_string: The String which is used for searching the substring.
3. Start_position: The starting index from where searching will start. It is completely optional.

### **NOTE**

1. By default, the starting index will be 1.
2. If the substring is not found within the string, then the function will return 0.

See the following examples.

```
SELECT CHARINDEX ('a', 'AppDividend.com');
```

See the output.

```
1
```

### **EXPLANATION**

As **a** was present in the first index, so 1 was returned as the output. As the function is not case sensitive, so, there was no error.

```
SELECT CHARINDEX ('p', 'Appdividend.com', 2);
```

See the output.

```
3
```

### **EXPLANATION**

As the starting index was from 2, so the function returned 3 as output. If the starting index was not 2, then the output would have been 2.

```
SELECT CHARINDEX ('IS', 'HONESTY IS THE BEST POLICY');
```

See the output.

```
9
```

### **EXPLANATION**

As IS was starting from the 9th index. Therefore, 9 was returned as output.

```
SELECT CHARINDEX ('J', 'AppDividend.com');

```

See the output.

```
0
```

### **EXPLANATION**

As J was not present in the given string. So, 0 was returned as output.

Let’s apply the function in a Table.

# **Table: Employee**

[Untitled](https://www.notion.so/ec2bcd1b714d48e1a72102e0c33f3110)

Now, suppose we want to count the number of characters before the “@” symbol form email column.

Then the following query has to be written,

### **QUERY**

```
Select Emp_id, Emp_name, CHARINDEX (‘@’, Email) AS Count 
from Employee;

```

### **Output:**

[Untitled](https://www.notion.so/4c2f7e7262674e688e43bd799014915d)

As you can see that the number of characters before “@” was displayed under the column named Count.

# **Using CHARINDEX() function to perform a case-insensitive search**

This statement shows a case-insensitive search for the string ‘**APPDIVIDEND**‘ in ‘This is appdividend CHARINDEX’:

```
SELECT 
    CHARINDEX(
        'APPDIVIDEND', 
        'This is appdividend CHARINDEX'
    ) position;
```
