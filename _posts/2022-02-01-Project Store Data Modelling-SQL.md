---
bg: "tools.jpg"
layout: post
title:  Project Store Data modelling-SQL
crawlertitle: Markdown sample
summary: Description for this article
date:   2022-02-01
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---

1 Identify the dataset

The store has several departments, both retail and administrative, located on different floors of a building. Each department has several employees working for it, and one boss who manages it: details of employees and bosses are stored in the same table.
The retail departments make sales. The items they sell are delivered by suppliers. Details of sales, suppliers and deliveries are recorded in the database.

[![Physical data model]({{ site.images | relative_url }}/Physical.png)]({{ site.images | relative_url }}/Physical.png)

2 Data in the tables

[![Table 1]({{ site.images | relative_url }}/Table1.png)]({{ site.images | relative_url }}/Table1.png)
[![Table 2]({{ site.images | relative_url }}/Table2.png)]({{ site.images | relative_url }}/Table2.png)

3 SQL Queries

3.1 Find the names of all employees in department number 1
Now add a condition to limit how many rows are returned, and to restrict our result to one column.

SELECT EmployeeName FROM Employee 
    WHERE DepartmentID = 1;

3.2 Find the items sold on floors other than the second floor

First look at the slightly simpler query: Which items are sold on the second floor?

SELECT DISTINCT ItemID
    FROM Sale INNER JOIN Department
        ON Sale.DepartmentID = Department.DepartmentID 
            WHERE DepartmentFloor = 2;

It’s simple now to change this to: Which items are sold on OTHER floors?

SELECT DISTINCT ItemID FROM Sale INNER JOIN Department 
    ON Sale.DepartmentID = Department.DepartmentID
        WHERE DepartmentFloor <> 2; 

The Natural Join syntax is simpler:
SELECT DISTINCT ItemID 
FROM Sale NATURAL JOIN Department
    WHERE DepartmentFloor <> 2;

Variation: find the items sold by at least two departments on the second floor

SELECT ItemID FROM Sale NATURAL JOIN Department 
    WHERE DepartmentFloor = 2
    GROUP BY ItemID
        HAVING COUNT(DISTINCT Department.DepartmentID) > 1;

3.3 For each item, give its type, the departments that sell the item, and the floor location of these departments
A simple three way join

SELECT Item.ItemName, ItemType, Department.DepartmentID, DepartmentFloor 
    FROM Item INNER JOIN Sale INNER JOIN Department 
    ON Sale.ItemID = Item.ItemID
    AND Sale.DepartmentID =
        Department.DepartmentID;

3.4 List suppliers that deliver a total quantity of items of types C and N that is altogether greater than 40

SELECT Delivery.SupplierID, SupplierName FROM Supplier 
    INNER JOIN Delivery INNER JOIN Item
ON Supplier.SupplierID = Delivery.SupplierID 
AND Item.ItemID = Delivery.ItemID
WHERE (ItemType = 'C' OR ItemType = 'N') 
GROUP BY Delivery.SupplierID, SupplierName
    HAVING SUM(DeliveryQTY) > 40;

3.5 Find the items sold by ALL departments on the second floor

SELECT Sale.ItemID FROM Sale NATURAL JOIN Department 
    WHERE Department.DepartmentFloor = 2
    GROUP BY Sale.ItemID
         HAVING count(DISTINCT Department.DepartmentID) =
             (SELECT count(DISTINCT DepartmentID) FROM Department
                  WHERE DepartmentFloor = 2);



