---
layout: post
title:  "How to Easily Create a Product via GraphQL"
ategories: shopify graphql
---

> Our objective in this exercise is to be able to **create** a **product** in Shopify using **GraphQL**.

In my previous post, I showed you [how to retrieve Shopify data via GraphQL](/how-to-access-shopify-data-from-your-app/){:target="_blank"}. This time, I'll show you how to **add** data (more specifically, a product) via GraphQL.

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
* `line 4:` `$input` is any variable name (as long as it has a `$` prefix,  makes sense and used consistently). [`ProductInput`](https://shopify.dev/docs/admin-api/graphql/reference/mutation/input-object/productinput?api[version]=2020-04){:target="blank"} is the expected [type](https://graphql.org/learn/schema/#type-language){:target="_blank"} of the variable `$input`.
* `line 4:` The `!` after `ProductInput` means that the `$input` variable is *required*.
* `line 5:` As mentioned, we now use the [Shopify `productCreate` mutation](https://shopify.dev/docs/admin-api/graphql/reference/mutation/productcreate?api[version]=2020-04){:target="_blank"}.
* `line 5:` Documentation reveals that [`productCreate`](https://shopify.dev/docs/admin-api/graphql/reference/mutation/productcreate?api[version]=2020-04){:target="_blank"} has `input` as one of its arguments, and the only one to be required. We just straight-up pass `$input` from `line 4` to `input`.
* `lines 6-9:` These lines describe a subset of the **return fields** that we are expecting to get and use. We just need `product.title` and `product.onlineStorePreviewUrl` in this example.



### 2.) Create a function that will execute your mutation

{% gist d59f8b3b731e94a50a3139732de1acce %}

Once our mutation query is all set and ready, we use the [`useMutation` hook](https://www.apollographql.com/docs/react/data/mutations/#usemutation-api){:target="_blank"} to create a function that will be executed at will, and several variables that act as references to return data and metadata.

* `line 4:` `createProduct` is the function to invoke to execute our mutation. This function needs to have the proper parameters to be invoked properly, and we shall see that later.
* `line 8:` `createProductData` holds the return value of the mutation query, and will be populated once the query is done. This is `nil` initially, so ensure that there are `nil` checks in your code when referring to `createProductData`.
* `lines 6:` `createProductLoading` holds the state whether the mutation query is still executing, or whether the query is done. Very useful to partner with spinners.


### 3.) Invoke your function and capture results

{% gist 09386b4b0df3463a29780095b4a27ddf %}

After all that preparation, this is where the magic actually happens. We chose an event when we want the query to be executed, then we pull the trigger. In this example, we choose a button click (i.e, form submission) as our event trigger.

What we are looking at is a form with the following [Polaris components](https://polaris.shopify.com/components/get-started){:target="_blank"}:

* `TextField` for **product name** (`line 49`)
* `TextField` for **product description** (`line 51`) 
* A `Banner` that will only be visible when our product is successfuly created (`lines 36-47`), and
* A submission `Button` that submits the form (`lines 54 - 59`)
* As cherry on top, a `Spinner` to indicate whether our query is still ongoing, or already done (`line 57`).

We also observe the following:

* Upon submission of the form, the `createProduct` mutation function is invoked via `onSubmitMutation` (`line 33, 15 - 28`).
* Notice that `createProduct` was invoked on `line 17-24` with an object parameter with `variables` key. This object will be used in lieu of the mentioned `$input` variable in our mutation query.  
* The values of the `TextField` forms in `line 49 & 51` is passed without modification to our mutation query at `lines 20 - 21`.
* On success, the `Banner` will display the product title return value via the variable `createProductData.productCreate.product.title` at `line 38`.
* Similarly, we can preview the new product page by redirecting to the url in the variable `createProductData.productCreate.product.onlineStorePreviewUrl` at `line 43`.

If the [reference application](https://github.com/klaudsol/shopify-app-under-20-minutes){:target="_blank"} is [run correctly](https://landing.klaudsol.com/shopify-app-in-20-minutes){:target="_blank"}, you should see something like this:

![Graphql Admin API Mutation Example](/assets/images/shopify20-49.png)

And we're done! :)

Next up, let's see how we can sell our Shopify app masterpiece at the [Shopify app store](https://apps.shopify.com/){:target="_blank"}.