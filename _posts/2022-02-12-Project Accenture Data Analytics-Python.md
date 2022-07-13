---
bg: "tools.jpg"
layout: post
title:  Project Accenture Data Analytics-Python
crawlertitle: Python Project
summary: Description for this article
date:   2022-02-12
categories: posts
tags: ['PROJECTS']
author: Irene Y.
bg: "african-penguins.jpg"
---
1.Project Understing

1.1 Client background
Over the past 5 years, the client has reached over 500 million active users each month. They have scaled quicker than anticipated and need the help of an advisory firm to oversee their scaling process effectively. Due to their rapid growth and digital nature of their core product, the amount of data that they create, collect and must analyze is huge. Every day over 100,000 pieces of content, ranging from text, images, videos and GIFs are posted. All of this data is highly unstructured and requires extremely sophisticated and expensive technology to manage and maintain. 

There are 3 main reasons why they are now looking at bringing in external expertise: 1) They are looking to complete an IPO by the end of next year and need guidance to ensure that this goes smoothly. 2) They are still a small company and do not have the resources to manage the scale that they are currently at. They could hire more people, but they want an experienced practice to help instead. 3) They want to learn data best practices from a large corporation. 

1.2 Tasks to be delegated: 
- Creation of an up-to-date big data best practices presentation 
- Extraction of sample data sets using SQL 
- On-site audit of their data-center 
- Merging of sample data set tables 
- Loading of sample data sets into Accenture sandbox database 
- Technology architecture workshop with Data Team to understand their technology landscape 
- Stress testing of their technology to identify weak spots 
- Communication with previous IPO companies within client base for reference stories 
- Analysis of sample data sets with visualizations 

2.Data Cleaning & Modeling

2.1 Requirements gathering

2.2 Data cleaning

[![Lighthouse]({{ site.images | relative_url }}/Python1.png)]({{ site.images | relative_url }}/Python1.png)

User
ID: Unique ID of the user (automatically generated)
Name: Full name of user
Email: Email address of user

Profile
User ID: Unique ID of a user that exists in the User table
Interests: Interests of the associated user
Age: Age of the associated user

Location
User ID: Unique ID of a user that exists in the User table
Address: Full address of the user

Session
User ID: Unique ID of a user that exists in the User table
Device: Mobile device that they used for this session on the application
Duration: Amount of time in minutes that this user stayed active on the application during this session

Content
ID: Unique ID of the content that was uploaded (automatically generated)
User ID: Unique ID of a user that exists in the User table
Type: A string detailing the type of content that was uploaded
Category: A string detailing the category that this content is relevant to
URL: Link to the location where this content is stored

Reaction
Content ID: Unique ID of a piece of content that was uploaded
User ID: Unique ID of a user that exists in the User table who reacted to this piece of content
Type: A string detailing the type of reaction this user gave
Datetime: The date and time of this reaction

ReactionTypes
Type: A string detailing the type of reaction this user gave
Sentiment: A string detailing whether this type of reaction is considered as positive, negative or neutral
Score: This is a number calculated by Social Buzz that quantifies how “popular” each reaction is. A reaction type with a higher score
should be considered as a more popular reaction.

Data Source:
https://www.theforage.com/modules/hzmoNKtzvAzXsEqx8/zjxeuu5mYzBuZw3fe?ref=D9gg2ESnLeyxJNQgv

2.3 Data modeling
[![Lighthouse]({{ site.images | relative_url }}/Python3.jpg)]({{ site.images | relative_url }}/Python3.jpg)

3.Data Visualization & Storytelling

[![Lighthouse]({{ site.images | relative_url }}/Python2.jpg)]({{ site.images | relative_url }}/Python2.jpg)

3.1 Data visualization
Use data set to create insightful visualizations to address the requirements of the project. 

3.2 Create a presentation
Ensure that the presentation of the results is clear and can be easily understood by internal team and the client. 

3.3 Storytelling
Make sure that throughout presentation incorporate storytelling. Make use of the techniques outlined in the additional resources and try to make the presentation as engaging and persuasive as possible. 

