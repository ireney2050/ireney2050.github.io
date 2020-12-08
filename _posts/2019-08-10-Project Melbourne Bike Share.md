
---
bg: "tools.jpg"
layout: post
title:  Project Melbourne Bike Share
crawlertitle: Markdown sample
summary: Description for this article
date:   2019-08-10
categories: posts
tags: ['PROJECTS']
author: Irene Y.
bg: "african-penguins.jpg"
---


Melbourne Bike Share (MBS) is a bike hire service that operates in Melbourne city. As a part of Melbourne’s public transportation, MBS is dedicated to provide a fit and green transport alternative to users. So far, it has 50 docking stations and possesses over 600 bikes, which helps reducing crowding during commuting time and handling increasing travel demands in inner Melbourne city.

Bike sharing has become a popular means of transportation nowadays, as it provides a new way to optimise social resources. However, it raises a range of problems at the same time, such as the issue of rebalancing the entire bike inventory across the city being serviced, each docking station demands to fill bikes timely to meet users’ needs at any time. This rebalancing can prove costly for bike sharing business, due to transportation and infrastructure demands. To address this issue, this article proposes an optimisation solution to minimise bike rebalancing cost.

![Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.20.43_pm.png](Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.20.43_pm.png)

There are four existing warehouses that can be used for storing bikes. There are 50 stations to supply the bikes with different demands. The stations are reduced by 1 from an official 51 stations as the 2 stations are almost in same area in the map thus combining the 2 stations would only require 1 trip to supply the bikes. These stations are all marked with blue flags in figure 1 below.

**Decision variables**

The decision variables below are used for minimizing the cost to achieve the optimization

with the following definition -

- y is 1 if to rent the warehouse in CBD, 0 otherwise.
- *xij* = units of bikes to be shipped from distribution warehouse *i* to station *i*

    *i.e. x11* is units of bikes to be shipped from distribution warehouse *1* (CBD warehouse) to
    Station *1* (Harbour Town Docklands). See chapter 5 Implementation for named list of
    warehouses and Stations.

**Objective function**

Below is the objective function of the model used in this proposal, additional context is
provided in the implementation section.

Minimize transportation cost (Z) = total transportation cost + total warehouse rental cost

𝑍=∑𝑛 ∑𝑚 𝐶𝑋 +𝑦×𝑅𝐶
𝑖=1 𝑗=1 𝑖𝑗 𝑖𝑗

**Where:**
    ◦  m = 1 to 4 and m is a warehouse

    ◦ n = 1 to 50 and n is a bike station

    ◦ **Cij** refers to the cost of transportation. (See chapter 4 for detailed definition of cost of

transportation)

    ◦ **Xij** = Units of bike to be shipped from warehouse j to station i

    ◦  **y** is 1 if to rent the warehouse in CBD, 0 otherwise.

    ◦  **RC** refers to the rental cost of the CBD warehouse. (See chapter 4 for detailed

definition of RC)

**y** = {1, 𝑖𝑓 𝑡𝑜 𝑟𝑒𝑛𝑡 𝑡h𝑒 𝑤𝑎𝑟𝑒h𝑜𝑢𝑠𝑒 𝑖𝑛 𝐶𝐵𝐷 ; 0, 𝑂𝑡h𝑒𝑟𝑤𝑖𝑠𝑒 }

**Xij** = Units of bike to be shipped from warehouse j to station i
**j** = warehouse 1 to 4**i** = stations 1 to 50

**4.2. Identify the objective function**

Our objective function is to minimise total transportation cost

𝑛𝑚

𝑍= ∑∑𝐶𝑖𝑗𝑋𝑖𝑗 +𝑦×𝑅𝐶
𝑖=1 𝑗=1

**m = 1 to 4
n = 1 to 50**

where:
**Cij** refers to the cost of transportation per bike per kilometre from warehouse j to

station I, **j** = warehouse 1 to 4 ; **i** = stations 1 to 50. Each pair of transportation cost is
calculated as

> **$2.16 * Distance * 2 / demand of each station**

For example, **C11** = $2.16 * 3.6 km * 2 / 16 = $0.97 per KM per bike**a.** An online resource was used to calculate the operating cost for our chosen method
of bike transportation, for a ‘Flat Deck’ type of truck, the estimated operating cost

is $2.16 / KM (Freight Metrics, 2018).**b.** The distance of each pair of transportation is derived from Google Maps by

keying in the exact coordinate of each bike station (retrieved from the government
website), and the address of each warehouse (retrieved from real estate website).
Further, the distances are multiplied by 2 to factor in the round trip consideration.

RC refers to the rental cost of the warehouse. In this case, the incremental cost only accounts for the rent of CBD warehouse whereas the rental costs of other warehouses are sunk costs. To calculate the rent for CBD warehouse, we took a reference from the real estate website, a 2 square meters storage in the CBD, which is $97.64 / month (Spacer, 2018). Accordingly, we assume the daily rent (takes 31 days in a month) of a 100 square meters warehouse approximately equals to $97.64 / 2 * 100 / 31 ≈ $157.5.

![Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.25.39_pm.png](Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.25.39_pm.png)

**Implementation:**

![Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.25.59_pm.png](Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.25.59_pm.png)

![Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.26.23_pm.png](Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.26.23_pm.png)

In addition, the model shows that it is more cost efficient to rent an additional
warehouse in CBD, given that the incremental cost of the CBD warehouse being
covered by total costs saved from the shorter distributing distance. Figures 6 & 6
below shows that the total cost incurred with renting the warehouse in CBD **($644.26)**
is cheaper than to distribute from the 3 warehouses alone in the inner suburbs
**($672.27).**

![Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.27.36_pm.png](Melbourne%20Bike%20Share%2062faa4ad135947fe93d0dfe01d5aaf34/Screen_Shot_2020-12-08_at_12.27.36_pm.png)

Although this proposed model contains many constraints and limitations, it successfully solved cost minimisation problem in bike rebalancing area, and as mentioned previously remains quite functional if viewed in a vacuum, without an awareness of the more complex and applicable models which have been applied in the past.