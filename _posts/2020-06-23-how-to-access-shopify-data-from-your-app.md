---
layout: post
title:  "How to Access Shopify Data From Your App"
ategories: shopify graphql
---
![GraphQL](https://mcusercontent.com/2258b1142d581e51c131c3e0e/images/03c35c6b-ec03-4df7-88b5-64b0acc4de95.png "How to Access Shopify Data From Your App")

*(This is part 3 of 3 of the **3 Technologies That You Need to Learn to Build Your Own Shopify App** mini-series)*

Hello developers!

To make our **Shopify app** valuable to merchants, we need to **retrieve** and **manipulate data** from our Shopify store. 

This will be the most exciting part for those into **number crunching**, **data analysis**, **data aggregation**, and **cross-systems** integration.

Available data for us includes Shopify **products**, **orders**, **customers**, and **shop data**, among other interesting data sets. 

Shopify CLI provides a **GraphQL layer** that gives us easy access to Shopify's data. This puts GraphQL as the our **Technology #3** that you need to learn to build your own Shopify app. 

## 3.) GraphQL
According to [graphql.org](https://graphql.org){:target="_blank"}, GraphQL is both the “[1.) query language for APIs and 2.) a runtime for fulfilling those queries with your existing data](https://graphql.org){:target="_blank"}”. 

It is then both the **query language** that we need to speak to get and change data, and at the same time it is also the **technology stack** that allows us to get data using the said query language.

What’s exciting is that Shopify CLI provides React Hooks (via [Apollo React Client](https://www.apollographql.com/docs/react){:target="_blank"}) that allows us to declare GraphQL queries from the **React level**. This makes app creation really fast, convenient (and arguably, fun). 

So, enough theory. How do we access Shopify data using GraphQL?

### 3.0) Ensure your Shopify app is running on your development environment

The instructions below will make more sense if you can run and play around with it. Thus, you need to ensure that you have a properly setup, authenticated, and running Shopify development app before proceeding.

If you need to quickly spin up a Shopify application, I suggest you download 


### 3.1) Build your GraphQL query inside your React application 
{% gist 7244d10d19780d390e1c26bcaa747962 %}
### 3.2) Create a function that will execute your query
### 3.3) Invoke your function


