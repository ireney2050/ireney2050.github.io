---
bg: "tools.jpg"
layout: post
title:  SQL Function Trim()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-01-06
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL TRIM function is used for removing spaces and characters from both ends of the string. The TRIM() function removes the space character OR other specified characters from the start or end of a string. By default, the TRIM() function removes leading and trailing spaces from a string.

# **SQL TRIM Function Example**

The syntax of the TRIM() Function is the following.

```
TRIM ([removed_characters FROM] input_string)
```

See the parameters of the TRIM() function.

1. re**moved_characters:** It is a literal, variable of any non-LOB character type contains characters which will be removed.
2. **input_string:** It is an expression that depicts the kind of characters to be removed.

# **Examples**

See the following query.

```
Select TRIM (‘   SQL TUTORIAL   ‘);

```

See the following output.

```
SQL TUTORIAL
```

Here, in the above example leading and trailing whitespaces were removed.

See the following query.

```
Select TRIM (‘@#’ FROM ‘123@456###’)

```

See the output.

```
123456

```

Here, in the above example, specified characters, i.e. **@** and **#,** are removed from the input_string.

LTRIM and RTRIM are the parts of the SQL TRIM function.

**LTRIM():** This function is used for removing whitespaces at the beginning of the string.

**Example:**

```
Select LTRIM (‘   Example For LTRIM    ‘);
```

See the output.

```
Example For LTRIM
```

**RTRIM ():** This function is used for removing whitespaces at the end of the string.

See the following query.

```
Select RTRIM (‘   Example For RTRIM      ’);

```

See the output.

```
Example For RTRIM

```

Above were the concepts which work in SQL SERVER.

Let’s see the working of the TRIM function in ORACLE.

See the following syntax.

```
TRIM ([ [{LEADING | TRAILING | BOTH}] [removal_char]
FROM] target_string [COLLATE collation_name])

```

### **PARAMETERS**

1. **LEADING: It depicts the leftmost part of the string.**
2. **TRAILING:** It depicts the rightmost part of the string.
3. **BOTH:** It depicts both the left and right part of the string.
4. **Removal_char:** It depicts the character to be removed.
5. **Target_string:** It depicts the string onto which action is to be taken.
6. **Collation_name:** It describes the collation to be applied to the string.

See the following query.

```
Select TRIM (TRAILING ‘1’ FROM 1234567891) FROM dual;

```

See the output.

```
123456789

```

Here, Trailing means rightmost part of the string, so one was deleted from the rightmost part of the string.

Let’s apply the TRIM function to a table.

Consider a table **Employee:**

[Untitled](https://www.notion.so/9df85fdb9691471a967d1124e7d5df49)

Now, suppose we want to remove the leading ‘m’ from First_name then the following query has to be used. See the following query.

```
Select TRIM (LEADING ‘m’ from First_name) From Employee;
```

See the output.

**First_name**

---

Aman

---

Avni

---

Karan

---

Suraj

---

Ravindran

---

Here, you can see that M was removed from the 1st position.

Let’s remove the trailing ‘n’ from the First_name then the following query has to be used.

See the following query.

```
Select TRIM (TRAILING ‘n’ from First_name) From Employee;

```

See the output.

**First_name**

---

Maman

---

Mavni

---

Kara

---

Suraj

---

Ravindra

---

Here, you can see that N was removed from the last position.