---
layout: post
title:  "How to Access Shopify Data From Your App"
ategories: shopify graphql
---
![GraphQL](https://mcusercontent.com/2258b1142d581e51c131c3e0e/images/03c35c6b-ec03-4df7-88b5-64b0acc4de95.png "How to Access Shopify Data From Your App")

> This is part 3 of 3 of the **3 Technologies That You Need to Learn to Build Your Own Shopify App** mini-series. <br /><br /> In this tutorial, we cover how to access Shopify data using **GraphQL**. <br /><br/>Our goal is to retrieve Shopify **shop metadata**, such as **domain name**, **subscription plan**, and **timezone** used using the [Shop](https://shopify.dev/docs/admin-api/graphql/reference/object/shop?api[version]=2020-04){:target="_blank"} [object](https://graphql.org/learn/schema/#:~:text=Object%20types%20and%20fields,appearsIn%3A%20%5BEpisode!%5D){:target="_blank"}.

Hello developers!

To make our **Shopify app** valuable to merchants, we need to **retrieve** and **manipulate data** from our Shopify store. 

This will be the most exciting part for those into **number crunching**, **data analysis**, **data aggregation**, and **cross-systems** integration.

Available data for us includes Shopify [**products**](https://shopify.dev/docs/admin-api/graphql/reference/object/product?api[version]=2020-04){:target="_blank"}, [**orders**](https://shopify.dev/docs/admin-api/graphql/reference/object/order?api[version]=2020-04){:target="_blank"}, and [**customers**](https://shopify.dev/docs/admin-api/graphql/reference/object/customer?api[version]=2020-04){:target="_blank"}, among other interesting data sets. 

Shopify CLI provides a **GraphQL layer** that gives us easy access to Shopify's data. This puts GraphQL as the our **Technology #3** that you need to learn to build your own Shopify app. (As a refresher, here's [Technology #1](https://us8.campaign-archive.com/?u=2258b1142d581e51c131c3e0e&id=07fac8376c&fbclid=IwAR2vmbMMT-Vo3wVmW9ybGOOVW6wV2AqpBWkrIQEMnN89qAAcnLuQQtVtIAM){:target="_blank"} and [Technology #2](https://us8.campaign-archive.com/?u=2258b1142d581e51c131c3e0e&id=98b52233a7&fbclid=IwAR1fbitPm4c-oES-97uLHoQTT4B1OhNtYmu927U4XfvUf_orvjDZLITtrK4){:target="_blank"}) 

## 3.) GraphQL
According to [graphql.org](https://graphql.org){:target="_blank"}, GraphQL is both the “[1.) query language for APIs and 2.) a runtime for fulfilling those queries with your existing data](https://graphql.org){:target="_blank"}”. 

It is then both the **query language** that we need to speak to get and change data, and at the same time it is also the **technology stack** that enables us to get data using the said query language.

What’s exciting is that Shopify CLI provides React Hooks (via [Apollo React Client](https://www.apollographql.com/docs/react){:target="_blank"}) that allows us to declare GraphQL queries from the **React level**. This makes app creation really fast and convenient (and I'd say more fun too!). 

So, enough chitchat. How do we access Shopify data using GraphQL?

### Objective

> To reiterate, our objective is to retrieve Shopify **shop metadata**, such as **domain name**, **subscription plan**, and **timezone** used using the [Shop](https://shopify.dev/docs/admin-api/graphql/reference/object/shop?api[version]=2020-04){:target="_blank"} [object](https://graphql.org/learn/schema/#:~:text=Object%20types%20and%20fields,appearsIn%3A%20%5BEpisode!%5D){:target="_blank"}.


### 3.0) Ensure your Shopify app is running on your development environment

The instructions below will make more sense if you can run and play around with it. Thus, you need to ensure that you have a **properly setup, authenticated, and running Shopify development app** before proceeding.

If you need to quickly spin up a Shopify application, I suggest you download our [tutorial on how to build your first Shopify app](https://landing.klaudsol.com/shopify-app-in-20-minutes){:target="_blank"}.

For convenience, a [sample implementation can also be found here](https://github.com/klaudsol/shopify-app-under-20-minutes/blob/master/pages/index.js){:target="_blank"}.

### 3.1) Build your GraphQL query inside your React application 
{% gist 7244d10d19780d390e1c26bcaa747962 %}

First step is to create a string GraphQL query in your React codebase as seen on the above snippet. Don't worry yet about the `gql` [tagged template literal](https://wesbos.com/tagged-template-literals){:target="_blank"} --- we'll get to that.

One thing that you'd notice is that GraphQL queries look like an "empty JSON shell" -- only the keys are provided, without values. This is intended as the return value will be an object with that exact same "shape" (i.e., use the same keys that you provided), but with the requested values filled in. 

To demonstrate, if we put the query result in `data`, the **subscription plan name** can be accessed via `data.shop.plan.displayName`. Once the lightbulb clicks, you'd be amazed how easy it is to query data.

* Line `4` declares that we intend to only `query` data, and not to change it. 
* Line `5` states that we query the [`shop` queryable object](https://shopify.dev/docs/admin-api/graphql/reference/object/shop?api[version]=2020-04){:target="_blank"} provided by Shopify.
* Lines `6 - 15` are fields of the `shop` object that we are interested in. Unlike a REST API response where you get all the fields whether you need them or not,  you can select as few or as many fields in your request. This is comparable to the `SELECT field1, field2, ...` statement in [SQL](https://en.wikipedia.org/wiki/SQL){:target="_blank"}. 
* You can also observe that some fields do not have children (such as `id`, `name`, `myshopifyDomain`, and `timezoneAbbreviation`). They are said to be as [scalars](https://shopify.dev/docs/admin-api/graphql/reference/scalar?api[version]=2020-04){:target="_blank"}, and we expect the response in these fields to be primitive data types.
* Some fields have children of their own (such as `primaryDomain` and `plan`) because we expect these fields to be populated with `objects`. As `objects`, they have their own fields and types. 

Let's now return to the reason we need the `gql` template literal tag. We need the `gql` tag to convert string into a syntax tree object for the GraphQL client. 

For us humans, representing the query as GraphQL strings is very visual and convenient. In one glance, we can easily "get" the structure of the request and the expected query response. However, for the GraphQL client, strings are "[are inconvenient to manipulate, if you are trying to do things like add extra fields, merge multiple queries together, or other interesting stuff.](https://www.npmjs.com/package/graphql-tag){:target="_blank"}". 

With that, our GraphQL query is ready to be used!

### 3.2) Create a function that will execute your query
### 3.3) Invoke your function and capture results


