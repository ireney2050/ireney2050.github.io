
---
bg: "tools.jpg"
layout: post
title:  SQL Injection
crawlertitle: Markdown sample
summary: Description for this article
date:   2018-08-05
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

SQL injection is a code injection technique that may lead to destroying your database. It is one of the most common web hacking techniques. It can also be defined as placement of malicious code in SQL statements from a web page input. Attackers can use the SQL Injection vulnerabilities to bypass the application security measures.

# **#What Is SQL Injection(S.I.)**

SQL Injection (SQLi) is the type of injection attack that makes it possible to execute the malicious SQL statements. These statements control the database server behind a web application.

The SQL Injection vulnerability may affect any website or web application that uses the SQL database such as SQL Server, MySQL, Oracle, SQL Server, or others.

Cyber Criminals may use it to gain unauthorized access to your sensitive data like customer information, personal data, trade secrets, and intellectual property, and much more top-secret information.

SQL Injection attacks are among the oldest, most prevalent, and the most dangerous web application vulnerabilities.

# **#SQL in Web Pages**

SQL injection usually occurs when we ask for a specific thing, and something other than that is given. For example, if we ask for the username/userId and instead of that, the user provides the SQL statement that will be unknowingly running in our database.

### **#Example**

In the following example, we will be creating the [Select statement](https://appdividend.com/2019/04/22/sql-select-query-example-sql-select-statement-tutorial/) by adding a variable for selecting a string.

```
Userid= getRequestString(“User_Id”);
txtSQL= ”Select * from Users where UserId = ”+Userid;

```

# **#1=1 based S.I.**

The main purpose of the code was to create the SQL statement to select a user with the userId.

The user can enter some “Smart” input of there is nothing to prevent a user from entering a “Wrong” input.

or example:

UserId: **105 OR 1=1**

See the following query.

```
Select * from users where userId =105 or 1=1;

```

The above SQL statement will return All rows from the “Users” table as OR 1=1 always results in True.

By using these techniques, the hacker might get all the information of users, including its username and password by simply inserting 105 OR 1=1 into the input field.

# **“=” based S.I.**

For example, if a web page contains the userId and password field, as shown below.

![https://appdividend.com/wp-content/uploads/2019/07/SQL-INJECTION.png](https://appdividend.com/wp-content/uploads/2019/07/SQL-INJECTION.png)

### **#Example**

```
UserName = getRequestString("Username");
Password = getRequestString("User_password");
```

Now, see the following code.

```
SQL = 'SELECT * FROM Users WHERE Name ="' + UserName + '" AND Pass ="' + Password + '"'

```

### **#Result**

```
Select * from Users where Name=”Shubh” AND Pass=”Password”
```

This is the approach that is used on the web for logging inside the users’ database.

But, A hacker can get access to usernames and passwords in the database by simply inserting “ OR “=” into the user name or password text box.

![https://appdividend.com/wp-content/uploads/2019/07/SQL-Tutorial.png](https://appdividend.com/wp-content/uploads/2019/07/SQL-Tutorial.png)

### **#Query**

```
SELECT * FROM Users WHERE Name ="" or ""="" AND Pass ="" or ""=""

```

The above SQL statement will return all the rows from the “Users” table as OR “=” is always true.

# **#SQL Injection Based On Batch SQL Statements**

Nowadays, most databases use batched SQL statements.

A Batched SQL statement is a group of SQL statements separated by a semicolon.

### **#Example**

```
Select * from Users; DROP TABLE Suppliers

```

Suppose, there is the following input.

UserId:

See the following query.

### **#Query**

```
SELECT * FROM Users WHERE UserId = 105; DROP TABLE Suppliers;

```

# **#SQL Parameters For Protection**

We use Parameters for protecting a website from SQL injection.

These parameters are the values that are added to the SQL query at the time of execution.

The SQL engine checks each parameter to ensure that it is correct for its column and not as a part of the SQL to be executed.

### **#Example**

```
txtNam = getRequestString("CustomerName");
txtAdd = getRequestString("Address");
txtCit = getRequestString("City");
txtSQL = "INSERT INTO Customers (CustomerName,Address,City) Values(@0,@1,@2)";
db.Execute(txtSQL,txtNam,txtAdd,txtCit);

```

# **#How and Why S.I. Attack Is Performed**

If we want to make an SQL Injection attack, the attacker must first find the vulnerable user inputs within a web page or web application.

The web page or web application that has the SQL Injection vulnerability uses such user to input directly in the SQL query. The attacker can create an input content.

Such content is often called the malicious payload and it is a key part of the attack. After the attacker sends this content through input, malicious SQL commands are executed in that database.

SQL is the query language that was designed to manage the data stored in the relational databases. You can use it to create, read, modify, and delete data.

Many websites and web apps store all the data in SQL databases. In some cases, you can also use the SQL commands to run the operating system commands. Therefore, the successful SQL Injection attack can have severe consequences.

1. Attackers can use the SQL Injection to find the credentials of other users in the database. They can then impersonate these users. The impersonated user may be the database administrator with all the database privileges.
2. SQL lets you select and output the data from a database. The SQL Injection vulnerability could allow the attacker to gain complete access to all data in the database server.
3. SQL also lets you alter data in the database and add new data. For example, in the financial application, the attacker could use the SQL Injection to change balances, void the transactions, or transfer the money to their account.
4. You can use SQL to delete the records from the database, even drop tables. Even if the administrator makes the database backups, the deletion of the data could affect the application availability until that database is restored. Also, backups may not recover the most recent data.
5. In many database servers, you can access the OS using the database server. This may be intentional or accidental. In such cases, the attacker could use an SQL Injection as the initial vector and then attack the internal network behind the firewall.

# **#How to Prevent an S.I.**

1. The only sure way to prevent the S.I. attacks are the input validation and parameterized queries, including the prepared statements.
2. The application code should never use an input directly.
3. A developer must sanitize all the inputs, not only web form inputs such as login forms. They must remove the potentially malicious code items such as single quotes.
4. It is also a better idea to turn off the visibility of database errors on your production sites. Database errors can be used with the SQL Injection to gain information about your database.
5. If you discover the S.I. vulnerability, for example, the vulnerability may be in open-source code. In such cases, you can use the web application firewall to sanitize your input temporarily.