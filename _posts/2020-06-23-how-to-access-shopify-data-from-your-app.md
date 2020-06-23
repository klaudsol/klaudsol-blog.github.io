---
layout: post
title:  "How to Access Shopify Data From Your App"
ategories: shopify graphql
---
*(This is part 3 of 3 of the **3 Technologies That You Need to Learn to Build Your Own Shopify App** mini-series)*

Hello developers!

To make our **Shopify app** valuable to merchants, we need to **retrieve** and **manipulate data** from our Shopify store. 

This will be the most exciting part for those into **number crunching**, **data analysis**, **data aggregation**, and **cross-systems** integration.

Available data for us includes Shopify products, orders, customers, and shop data, among other interesting data sets. 

Shopify CLI provides a way for us a mechanism to access data via GraphQL. 

This puts GraphQL as the 3rd technology that you need to learn to build your own Shopify app. 

## 3.) GraphQL
According to graphql.org, GraphQL is a “1.) query language for APIs and 2.) a runtime for fulfilling those queries with your existing data”. 

What’s exciting is that Shopify CLI provides React Hooks (via Apollo Client)  that allows us to declare GraphQL queries from the React layer. This makes app creation really fast, convenient (and arguably, fun). 


{% gist 7244d10d19780d390e1c26bcaa747962 %}

