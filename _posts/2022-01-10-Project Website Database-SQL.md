---
bg: "tools.jpg"
layout: post
title:  Project Website Data modelling-SQL
crawlertitle: SQL Project
summary: Description for this article
date:   2022-01-10
categories: posts
tags: ['SQL']
author: Irene Y.
bg: "african-penguins.jpg"
---
Different types of data that we can get on a website.

We have traffic coming from a variety of sources that could be email, social media, search, direct traffic, and that's coming to a page on a website. Then it may visit another page, then you may take a product and put it into a shopping cart and finally make purchases and then data would flow into a payment.

[![SQL]({{ site.images | relative_url }}/web2.png)]({{ site.images | relative_url }}/web2.png)

Data will be going to Google Analytics tracking all of this or again, could be an internal system. We could have data writing to a MySQL database. It's great for aggregate things like how many sessions did I get on my site?
How much traffic did I get from organic?

We have traffic coming in, people hitting certain pages, putting products into the cart, making
purchases, and all of this information ends up getting stored so that the business can use it to analyze performance and make optimizations. We may track a user ID, we may have some sort of a field to say whether or not it's a repeat session or it's a new customer. We do all of this using cookies, so basically a cookie is a little snippet of code that is put in your browser when you visit a website, it has an identifier related to it.

[![WEBSITE]({{ site.images | relative_url }}/web1.png)]({{ site.images | relative_url }}/web1.png)

Starting to tie website page view data into the rest of the data that in the database. Mali has come back with this February page, new data that she was able to pull out of the Web analytics tool.

Create a table, open it and close it and and the query and first will have a website, page, view ID column, and that'll be a big int will have a created at timestamp and that'll be a date time.
We've got our website session, and so that's what we'll tie back to the website sessions table and that'll be a big int's and we'll have a preview URL.

Then we have website page views and are ready to import data. The website sessions data, a record is created when the first page loads, but no additional records are created throughout the rest of the session.

[![SQL QUERIES]({{ site.images | relative_url }}/web3.png)]({{ site.images | relative_url }}/web3.png)