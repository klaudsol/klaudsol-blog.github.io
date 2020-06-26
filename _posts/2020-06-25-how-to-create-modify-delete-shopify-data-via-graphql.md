---
layout: post
title:  "How to Create, Modify, and Delete Shopify Data via GraphQL"
ategories: shopify graphql
---

> Our objective in this exercise is to be able to **create**, **update**, and **delete** a **product** in Shopify using **GraphQL**.

In my previous post, I showed you [how to retrieve Shopify data via GraphQL](/how-to-access-shopify-data-from-your-app/){:target="_blank"}. This time, I'll show you how to **create**, **modify**, and **delete** data via GraphQL.

You can click here to view [reference code](https://github.com/klaudsol/shopify-app-under-20-minutes/blob/master/pages/index.js){:target="_blank"} used for this exercise.

To get the most out of this, I suggest you [quickly setup your own Shopify app on your development environment](https://landing.klaudsol.com/shopify-app-in-20-minutes){:target="_blank"}. Run, test, play around, and even destroy the code. You will appreciate this guide more, and you will learn faster. 

As that good old Chinese proverb says (now a cornerstone of my life), "I hear, I forget. I see, I remember, I do, I understand."

> I hear, I forget. <br /> I see, I remember.<br /> I do, I understand. <br /> - *Chinese Proverb*.

Let's get started, shall we?

## Creating a new product 


### 1.) Build your GraphQL mutation query

{% gist 6ff08e891dca12859058324bb805b770 %}

All of our GraphQL statements, whether *query* or *mutation*, will be plain old strings, which then be placed inside a `gql` [tagged template function](https://wesbos.com/tagged-template-literals){:target="_blank"} (Line `3`). The `gql` function converts our **string** query into a **syntax tree object** that the [Apollo GraphQL client](https://www.apollographql.com/client/){:target="_blank"} readily understands.

* `line 4:` The [operation type](https://graphql.org/learn/queries/#operation-name){:target="_blank"} `mutation` declares that we intend to change Shopify's data.
* `line 4:` `productCreate` is our [operation name](https://graphql.org/learn/queries/#operation-name){:target="_blank"}, and can be *anything*, in fact. We just chose `productCreate` for consistency as it will be solely using the [Shopify `productCreate` mutation](https://shopify.dev/docs/admin-api/graphql/reference/mutation/productcreate?api[version]=2020-04){:target="_blank"} in line `5`.  
* `line 4:` `($input: ProductInput!)` tells us that the query is expecting a [GraphQL variable](https://graphql.org/learn/queries/#variables){:target="_blank"} as input. This variable will be provided later when we invoke the function that will execute this mutation.
* `line 4:` `$input` is any variable name (as long as it has a `$` prefix,  makes sense and used consistently). [`ProductInput`](https://shopify.dev/docs/admin-api/graphql/reference/mutation/input-object/productinput?api[version]=2020-04){:target="blank"} is the expected [type](https://graphql.org/learn/schema/#type-language){:target=""_blank} of the variable `$input`.
* `line 4:` The `!` after `ProductInput` means that the `$input` variable is *required*.
* `line 5:` As mentioned, we now use the [Shopify `productCreate` mutation](https://shopify.dev/docs/admin-api/graphql/reference/mutation/productcreate?api[version]=2020-04){:target="_blank"}.
* `line 5:` Documentation reveals that [`productCreate`](https://shopify.dev/docs/admin-api/graphql/reference/mutation/productcreate?api[version]=2020-04){:target="_blank"} has `input` as one of its arguments, and the only one to be required. We just straight-up pass `$input` from `line 4` to `input`.
* `lines 6-9:` These lines describe a subset of the **return fields** that we are expecting to get and use. We just need `product.title` and `product.onlineStorePreviewUrl` in this example.



### 2.) Create a function that will execute your mutation

{% gist d59f8b3b731e94a50a3139732de1acce %}

### 3.) Invoke your function and capture results

{% gist 09386b4b0df3463a29780095b4a27ddf %}

## Updating an existing product

## Deleting an existing product