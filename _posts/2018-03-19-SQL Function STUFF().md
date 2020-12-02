---
bg: "tools.jpg"
layout: post
title:  SQL Function Stuff()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-03-19
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL STUFF() is an inbuilt function that is used to replace the sequence of characters from the source string of given length from the new string given at the time of input to the function. It is replaced from the index which is also specified at the time of input. The STUFF() function deletes the part of the string and then inserts another part into the string, starting at the specified position.

# **SQL STUFF Function Example**

See the syntax of stuff() function.

```
SELECT STUFF (source_string, start, length, add_string);

```

**PARAMETERS**

1. **source_string:** It is the string that is to be processed.
2. **Start:** It is an integer that is used for identifying the position to start deletion and insertion. If start is negative, zero, or longer than the length of the source_string, then the function will return NULL.
3. **add_string:** It is a substring that is used for replacement in the source_string.
4. **Length:** It specifies the number of characters to be deleted.

**Note:**

1. If the length is negative, the function will return NULL.
2. If the length is longer than the length of the source_string, then the function will delete the whole string.
3. If the length is zero, the function will insert the **add_string** at the position specified by the **Start** index.

# **Examples**

See the following query.

```
SELECT STUFF (‘appdividend.com’, 1, 11, ’APPDIVIDEND’);

```

See the output.

```
APPDIVIDEND.com

```

Here, in the above example, **appdividend,** which was of length 11, was replaced by **APPDIVIDEND**.

See the following query.

```
SELECT STUFF ('SQL Tutorial', 1, 3, 'SQL Server');

```

See the output.

```
SQL Server Tutorial
```

Here, in the above example Stuff () function deleted the first three characters from **SQL Tutorial** and then inserted **SQL Server** at its beginning position.

See the following query.

```
SELECT STUFF ('1936', 3, 0, ':');

```

See the output.

```
19:36

```

Here, in the above example, Colon (:) was inserted at the 3rd position which converted (HHMM) format to (HH: MM). See the following query.

```
SELECT STUFF (08312019, 3, 0, ‘/’), 6, 0, ‘/’);

```

See the following output.

```
08/31/2019

```

Here, in the above example, the STUFF () function converted (MMDDYYYY) format to (MM/DD/YYYY).

See the following query.

```
SELECT STUFF (‘Appdividend.com’, 12, 4, ‘is a great site!’);

```

See the output.

```
Appdividend is a great site!

```

Here, in the above example, **.com,** which was of length 4, was replaced by **is a great site**.
