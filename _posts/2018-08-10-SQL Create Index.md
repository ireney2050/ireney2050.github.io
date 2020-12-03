---
bg: "tools.jpg"
layout: post
title:  SQL Create Index
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-08-10
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"

SQL CREATE INDEX statement is used to create the indexes in the tables. Indexes are used to retrieve the data from the database very fast. The users cannot see the indexes, and they are just used to speed up the searches/queries. Updating the table with indexes takes more time than updating the table without (because the indexes also need the update). So, only create indexes on the columns that will be frequently searched against.

# **#What is an Index in SQL**

The index is a performance-tuning method of allowing the faster retrieval of records.

SQL index creates the entry for each value that appears in the indexed columns.

Each index name must be unique in the database.

# **SQL CREATE INDEX Example**

SQL Indexes are used to improve the efficiency of searches for data, presenting the data in the specific order when [joining](https://appdividend.com/2019/06/13/sql-joins-tutorial-for-beginners-sql-joins-example/) tables (see the “[JOIN](https://appdividend.com/2019/06/13/sql-joins-tutorial-for-beginners-sql-joins-example/)” Guides) and more.

An index is a “system” object, meaning that the database manager uses it.

Part of this usage is for the DBMS to update the index when the data used by index changes in the related table.

Keep this in mind because as the number of indexes increase in the database, overall system performance can be impacted.

If you find that your SQLs are running slow on the given table or tables, creating the index is the first thing to consider to correct that issue.

See the following syntax of CREATE INDEX.

```
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

See the following example.

```
CREATE INDEX IDX_ProductName
ON Products (ProductName);
```

In the above query, we have created an index called **IDX_ProductName** on the **Products** table, and the column name is **ProductName**.

If you want to create the index on the combination of columns, you can list all the column names within the parentheses, separated by commas. See the following query.

```
CREATE INDEX IDXname
ON Products (ProductName, id);
```

In the above query, we have changed the syntax name, and we have added two columns.

1. ProductName
2. id

A **simple index** is an index on the single column, while the **composite index** is an index on two or more columns. In the examples above, **ProductNameIx** is the simple index because there is only one column, while **IDX_proname_id** is the composite index because there are two columns.

There is no strict or universal rule on how to name the index. The generally accepted method is to place the prefix, such as “IDX_,” before the index name to avoid confusion with other database objects.

It is also a great idea to provide a piece of information on which table and column(s) the index is used on.

Here one thing you need to note that the exact syntax for **CREATE INDEX** may be different for the different DBMS. You should consult with your database manual for the related database syntax.

# **#Unique Index in SQL**

Similar to a [primary key](https://appdividend.com/2019/06/27/sql-primary-key-tutorial-with-example-primary-key-in-sql/), a unique key allows you to choose one column or combination of columns that must be unique for each record. Although you can only have one primary key on a table, you can create as many unique indexes on a table as you need.

If we want to create a unique index on the table, you need to specify a UNIQUE keyword in the CREATE INDEX statement.

See the following example.

```
CREATE UNIQUE INDEX IDX_ProductName
  ON Apps (ProductName);
```

In the above query, we have created an index called IDX_ProductName on the Apps table. The column name on which we are indexing is here **ProductName.**

The above example would create a unique index on the ProductName field so that this field must always contain a unique value with no duplicates.

This is a great way to enforce the integrity within your database if you require the unique values in the columns that are not part of your primary key.