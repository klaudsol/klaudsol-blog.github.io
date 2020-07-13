---
layout: post
title:  "How to Add Billing Code to Your Shopify App"
categories: shopify billing
---

> *One of the most common mistakes of beginning Shopify app developers is to assume that the Shopify app store will handle pricing and billing for them. Learn how to add billing code to your app to prevent selling it for free.*

If you published a public app without the appropriate billing code, your hard work would be distributed without any compensation (aka "moolah"). This will cause you lots of grief and heartache if the "giveaway" is not exactly intentional. 

It is also rather impossible to contact and manually charge each merchant who downloaded your app. This is especially true if your app stirred demand from thousands of merchants.

Before submitting that app for review, you must double-check if you added the billing code.

## Use Shopify CLI to Add Billing Code Template
Fortunately, [Shopify CLI](https://www.shopify.com.ph/partners/blog/cli-tool){:target="blank"} provides an effortless way to add billing code to our apps. 

{% gist c57f9b5a892ba0cb231e5bbe791df8a2 %}

Typing the code above will add billing logic to the file `server/server.js`. 

![How would you like to charge for your app?](/assets/images/shopify-billing-1.png)

For this example, we select **Recurring Billing**. You will want to pick this, too, if you're going to earn monthly recurring revenue from Shopify.

![server/server.js will be modified](/assets/images/shopify-billing-2.png)

Your `server/server.js` would like similar to this **before** generating the billing code.

{% gist 57321792df831c7a6ce907dbfa9c055e %}

**After** generating the billing code.

{% gist 92071062f3d852b8ba9aee7f78b840e7 %}

When that's done, let's adjust the price to be billed.

## Check and Modify Price 
What file to modify depends on whether you chose [**Recurring Billing**](#recurring-billing) or [**One-Time Billing**](#one-time-billing) in the previous selection. 

### Recurring Billing
You will need to head to `server/handlers/mutations/get-subscription-url.js`. For now, you can simplify your plan by having one subscription plan.   

{% gist fedcb5cafcb49bf13738c600ee4a37ac %}

The most important things to consider are:
* Plan name (`line 5`)
* Plan price (`line 12`)
* Currency (`line 12`)
* Trial Days (`line 8`)

It is best to give customers a free trial to make them feel that they are not taking any risks when evaluating your app.

* Is Test? (`line 7`)

You need to modify this logic to be `true` when using in development stores. Switch this to `false` right before publishing to enable actual billing to production stores. Better yet, have an environmental flag to detect whether you intend to develop or deploy in production.

### One-Time Billing
This time, locate `servers/handlers/mutations/get-one-time-url.js`, and modify the plan name and price accordingly.

{% gist 27380f4cb17b77334076865d41b7ae81 %}

Similar to the Recurring Billing above, you need to look out for the following:
* Plan name (`line 5`)
* Plan price (`line 6`)
* Currency (`line 6`)
* Is Test? (`line 8`)

## Test if Billing Code Works
When all is set and ready to rumble, launch your app, and visit your development store to see if the billing code kicked in.

Some things to consider when testing:
* Make sure that you created a **public app** when testing for billing code. Adding billing code to a custom app will throw you an error.
* The `test` flag must be set to true to prevent unwanted charges to you.

### Install the public app in a development store.

![](/assets/images/shopify-billing-3.png)

Head to the app dashboard, proceed to "Test your app," and select your development store.

![](/assets/images/shopify-billing-4.png)

Click the "Install App" button.

![](/assets/images/shopify-billing-5.png)

Click the  "Install unlisted app" button.

### Check if billing confirmation page is working properly.

![The billing confirmation page](/assets/images/shopify-billing-6.png)

If everything has been done correctly, you should see the above billing confirmation page. Double-check the plan name, price, and currency. 

Don't forget to properly configure your Paypal account so that Shopify knows where to deposit the money when customers purchase your app.

*Learned anything from this tutorial? Got further questions that haven't been answered yet? Comment your queries below, and I'll get back to you as soon as I can.*
