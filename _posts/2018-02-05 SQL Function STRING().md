---
bg: "tools.jpg"
layout: post
title:  SQL Function String()
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-01-06
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL String functions are used for manipulating the strings. Here, in SQL, we provide the string as input and then after applying string functions desired manipulated string is obtained.

# **SQL String Functions**

See the following String Functions.

# **#ASCII()**

**[SQL ASCII](https://appdividend.com/2019/09/16/sql-ascii-function-example-ascii-function-in-sql/) function is used for finding the ascii value of the character i.e. the numeric value. If more than one character is inserted within the function then the leftmost character value will be displayed. Here, we are using [SQL SELECT](https://appdividend.com/2019/04/22/sql-select-query-example-sql-select-statement-tutorial/) Statement.**

### **#Syntax**

```
SELECT ASCII('ab');
```

### **#Output**

```
97
```

# **#CHAR_LENGTH()**

The char_length() function is used for finding the length of a word.

### **#Syntax**

```
SELECT char_length('Shubh');
```

### **#Output**

```
5
```

# **#CHARACTER_LENGTH()**

The character_length() function is used for returning the length of an entire string.

### **#Syntax**

```
SELECT CHARACTER_LENGTH ('God Is Great');

```

### **#Output**

```
12
```

# **#CONCAT()**

[SQL concat()](https://appdividend.com/2019/08/27/sql-concat-function-example-concat-in-sql-tutorial/) function is used for adding two words or strings. It may have one or more arguments, if all arguments are non-binary strings, then the result is a non-binary string.

### **#SYNTAX**

```
SELECT CONCAT ('My', 'S', 'QL');
```

### **#OUTPUT:**

```
MySQL
```

# **#CONCAT_WS()**

[SQL concat_ws()](https://appdividend.com/2019/09/27/sql-concat_ws-function-example-concat_ws-method-in-sql/) is used for adding two words or strings with a symbol as concatenating symbol.

### **#Syntax**

```
SELECT CONCAT_WS ('_', 'God', 'is', 'Great');
```

### **#Output**

```
God_is_Great
```

# **#FIND_IN_SET()**

The find_in_set() function is used for finding a symbol from a set of symbols. This mainly returns the position in which the symbol is present.

### **#Syntax**

```
SELECT FIND_IN_SET ('b', 'a, b, c, d, e, f');
```

### **#Output**

```
2
```

# **#FORMAT()**

[SQL format()](https://appdividend.com/2019/11/07/sql-format-function-how-to-format-function-in-sql-server/) function is used for displaying a number in the given format.

### **#Syntax**

```
SELECT Format ("0.981", "Percent");
```

### **#Output**

```
‘98.10%’
```

# **#INSERT()**

SQL insert() function is used for inserting the data into a database.

### **#SYNTAX:**

```
INSERT INTO database (Id, Name) VALUES (1, 'Shubh');
```

# **#INSTR()**

**The instr() function is used for finding the occurrence of an alphabet. It generally displays the first occurrence of the string.**

### **#Syntax**

```
SELECT INSTR ('God is Great', 'e');
```

### **#Output**

```
11
```

# **#LCASE():**

The lcase() function is used for converting the given string into lower case.

### **#Syntax:**

```
SELECT LCASE ("Welcome to Appdividend”);
```

### **#Output**

```
Welcome to appdividend
```

# **#LEFT()**

The left() function is used for selecting a substring from the left of given size or characters.

### **#Syntax**

```
SELECT LEFT ('Appdividend.com', 5);
```

### **#Output**

```
Appdi
```

# **#LENGTH()**

The length() function is used for finding the length of a word.

### **#Syntax:**

```
SELECT LENGTH('Shubh');
```

### **#Output**

```
13
```

# **#LOCATE()**

The locate() function is used for finding the nth position of a given word in the string.

### **#Syntax**

```
SELECT LOCATE ('is', 'GodisGreat', 1);
```

### **#Output**

```
4
```

# **#Lower()**

The lower() function is used for converting the upper-case string into lower case.

### **#Syntax**

```
SELECT LOWER ('APPDIVIDEND.COM');
```

### **#Output**

```
appdividend.com
```

# **#LPAD()**

The lpad() function is used for returning the string argument, left-padded with the specified string.

### **#Syntax**

```
SELECT LPAD ('Shubh', 8, '0');
```

### **#Output**

```
000Shubh
```

# **#LTRIM()**

The ltrim() function is used for cutting the given substring from the original string.

### **#Syntax**

```
SELECT LTRIM ('44App', '44');
```

### **#Output**

```
App
```

# **#MID()**

The mid() function is used for returning a substring starting from the specified position.

### **#Syntax**

```
Select Mid ("LoveisLife", 6, 2);
```

### **#Output**

```
sLi
```

# **#POSITION()**

The position() function is used for finding position of the first occurrence of a given alphabet.

### **#Syntax**

```
SELECT POSITION ('e' IN 'AppDividend');
```

### **#Output**

```
9
```

# **#REPEAT()**

The repeat() function is used for writing the given string again and again till the number of times mentioned.

### **#Syntax**

```
SELECT REPEAT ('SQL', 2);
```

### **#Output**

```
SQLSQL
```

# **#REPLACE()**

The replace() function is used for cutting the given string in a function by removing the given substring.

### **#Syntax**

```
SELECT REPLACE ('123App123', '123');
```

### **#Output**

```
App
```

# **#REVERSE()**

The reverse() function is used for reversing a string specified inside a function.

### **#Syntax**

```
SELECT REVERSE('Shubh');
```

### **#Output**

```
hbuhs
```

# **#RIGHT()**

The right() function is used for selecting a substring from the right end of the given size.

### **#Syntax**

```
SELECT RIGHT ('AppDividend.com', 4);
```

### **#Output**

```
.com
```

# **#RPAD()**

The rpad() function is used for making a given string as long as the given size by adding the given symbol on the right.

### **#Syntax**

```
SELECT RPAD ('Shubh', 8, '0');
```

### **#Output**

```
Shubh000
```

# **#RTRIM()**

The rtrim() function is used for cutting a part of the string from the original string.

### **#Syntax**

```
SELECT RTRIM ('Shubhxyz', 'xyz');
```

### **#Output**

```
Shubh
```

# **#SPACE()**

The space() function is used to writing a given number of spaces.

### **#Syntax**

```
SELECT SPACE(7);
```

### **#Output**

‘       ‘

# **#STRCMP()**

The strcmp() function is used to compare the two strings.

1. If string1 and string2 are the same, then the STRCMP function will return 0.If string1 is smaller than string2, then the STRCMP function will return -1.If string1 is larger than string2, then the STRCMP function will return 1.

### **#Syntax**

```
SELECT STRCMP ('google.com', 'AppDividend.com');
```

### **#Output**

```
1
```

# **#SUBSTR()**

The substr() function is used for finding a substring from the given string and its position specified within the function.

### **#Syntax**

```
SELECT SUBSTR ('GodisGreat', 1, 5);
```

### **#Output**

```
Godis
```

# **#SUBSTRING()**

The substring() function is used for finding an alphabet from the mentioned size and the given string.

### **#Syntax**

```
SELECT SUBSTRING ('AppDividend.com', 9, 1);
```

### **#Output**

```
e
```

# **#SUBSTRING_INDEX()**

The substring_index() function is used for finding a substring before the given symbol specified within a function.

### **#Syntax**

```
SELECT SUBSTRING_INDEX ('www.AppDivivdend.com', '.', 1);
```

### **#Output**

```
www
```

# **#SOUNDEX (str):**

**The soundex() function is used for returning the Soundex string.**

**A Soundex string is four characters long, but the function returns an arbitrarily long string. We can use [SUBSTRING()](https://appdividend.com/2019/08/30/sql-substring-function-example-substring-in-sql/) function on the result to get a standard Soundex string.**

**All non-alphabetic characters in str are ignored, and all international alphabetic characters outside the A-Z range are treated as vowels.**

### **#SYNTAX**

```
SELECT SOUNDEX('Hello');
```

### **#OUTPUT**

```
H400
```

# **#TRIM()**

The trim() function is used for cutting the given symbol from the string mentioned.

### **#Syntax**

```
SELECT TRIM (LEADING '0' FROM '000123');
```

### **#Output**

```
123
```

# **#UCASE()**

The ucase() function is used for making the given string into upper case.

### **#Syntax**

```
SELECT UCASE ("Appdividend");
```

### **#Output**

```
APPDIVIDEND
```

# **#UNHEX (str)**

**It is used for converting given hexadecimal characters to digits or ascii characters.**

### **#Syntax**

```
SELECT UNHEX('4D7953514C');
```

### **#Output**

```
SQL
```