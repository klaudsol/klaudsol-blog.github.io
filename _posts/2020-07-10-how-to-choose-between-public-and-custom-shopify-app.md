---
layout: post
title:  "How to Choose Between Public and Custom Shopify App?"
categories: shopify billing app-types
---

![How to Choose Between Public and Custom Shopify App?](/assets/images/app-types.png)
*When creating a Shopify App, you will need to choose early on whether you will be creating a Custom App and a Public App. Learn when to choose either type.*

Creating a Shopify app can be a mentally demanding endeavor, especially for beginners.

Aside from a laundry list of technologies you need to learn and be familiar with, you need to make several decisions early on. Choosing between a **Custom App** and a **Public app** is one of those choices.

In this article, I shall try to ease your burden and help you decide when to choose a **Public App**, and when to select a **Custom App**.

## Choose a Public App When…
First, let's dissect what we get when we create a public app.
> ✔️ Unlimited merchant installs

There is no limit to how many unique merchants can install your app. This is in stark contrast to a [Custom App](#choose-a-custom-app-when), as we shall see later on.

> ✔ Reviewed by Shopify to protect trust and security

Public apps must pass the [Shopify review process](https://shopify.dev/concepts/app-store/getting-your-app-approved/review-process){:target="blank"} to be allowed to be installed on production stores. No passing review, no permission to be installed.

> ✔ Listed in the Shopify App Store (optional)

Being listed in the [Shopify App Store](https://apps.shopify.com/){:target="blank"} is THE best way to advertise and get your app known. The majority of the users use the **Search** feature of the Shopify App Store to look for solutions to their problems.

**So, when do you choose to create a Public app, then?**

### 1.) When you want to earn monthly recurring revenue.

![Monthly recurring revenue](/assets/images/public-vs-custom-1.jpg)
*Alright, my monthly recurring revenue from my app just came in! <span>Photo by <a href="https://unsplash.com/@cmophoto?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">cmophoto.net</a> on <a href="https://unsplash.com/s/photos/beach-hammock?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

If the primary reason you are into Shopify app development is to develop apps that will give you **regular monthly income streams**, you *need* to create a public app. 

You want your app to have the **maximum number of downloads**, and you want the **broadest reach possible** (obviously to have the **highest revenue**). 

At the same time, you do not want the inconvenience of manually charging and collecting from all of your merchant customers every single month. You want this thing automated and running in the background.

Choosing to create a public app gives you two benefits:
#### 1.1) You get free advertising to merchants all over the world.
If you create a public app, you can list it in the Shopify App Store listing. You will be provided with your own app pages to showcase the benefits of your app to the merchants. 

Being listed on the Shopify App Store is an excellent way to let merchants know that your app exists. When faced with problems with their shops, merchants will first visit the App Store to see if there is any available solution.  

#### 1.2) Monthly charging and collection are done automatically. 
By invoking the [Billing API](https://shopify.dev/tutorials/bill-for-your-app-using-graphql-admin-api){:target="blank"} from your code,  payment is taken automatically from the merchant. Shopify then holds the amount and deposits it to your Paypal account upon reaching $25 or more. 

This offloads you with lots of headaches such as invoicing, charging, currency conversion, and merchants' inability to pay on time.

In a future post, we shall discuss how to add billing code to your app to enable automatic monthly recurring charges.

### 2.) When you want to get your name out and market.
![Notice me senpai!](/assets/images/public-vs-custom-2.jpg)
*Notice me senpai! <span>Photo by <a href="https://unsplash.com/@marianna_ole?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Marianna OLE</a> on <a href="https://unsplash.com/s/photos/anime-girl?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

If your purpose is to get your name out via a free app in preparation for a paid version or a paid tier, then choosing to create a public app is the way to go, by the same virtue of the power of the Shopify app store search. If you solve a universal pain point, your solution will be downloaded by thousands of merchants worldwide. That's powerful marketing without spending another dime.

### 3.) When you have time allotted for an app review.
![Yep, we have time.](/assets/images/public-vs-custom-3.jpg)
*<span>Photo by <a href="https://unsplash.com/@devano23?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Devon Janse van Rensburg</a> on <a href="https://unsplash.com/s/photos/time?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

One major drawback of choosing to create a public app is not being able to use it outright. It takes roughly **a week** to get your app reviewed, and from experience, it seems that the Shopify app review team performs a mixture of automated and manual testing on your app. 

Also, expect that your app can get rejected. Though you may fix your app and resubmit, keep in mind that this time is taken against your schedule. Planning for ample time for review and correction is a must when choosing the public app route.

If you need to use the app NOW (or yesterday as your boss would have said), then selecting to create a public app is not the best way to go.

## Choose a Custom App When…

Before we proceed, let's review what we are getting when we opt for a custom app.

> ✔️ Limited to use by one merchant

Unlike public apps, custom apps are tied to only one merchant shop.

> ✔️ Not reviewed by Shopify.

You do not need Shopify's permission to use your app. You can use it **immediately** after deployment.

> ✖️ Can't be converted into a sales channel

Sales channels are usually connectivity to marketplaces outside Shopify, such as Facebook Marketplace, Messenger, Instagram, or Amazon. We shall further discuss Shopify sales channels in future posts. 

> ✖️ Can't use the Billing API to charge merchants

You cannot program any automation to charge your merchants. Your client should pay you via some other channel that has been agreed beforehand. This also means that you need to issue invoices manually and ensure that your client does indeed pay.

**When do we choose to create a Custom App?**

### 1.) When freelancing for a client.
![Most likely a freelance developer. Maybe.](/assets/images/public-vs-custom-4.jpg)
*Most likely a freelance developer. Maybe. <span>Photo by <a href="https://unsplash.com/@pmillerd?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Paul Millerd</a> on <a href="https://unsplash.com/s/photos/freelance?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

Your client would possibly want exclusive use of the app that you have been commissioned to make. Also, it would be entirely unnecessary to have Shopify review the app, as no one else aside from your client will see and use the app. 

Making a public app for your freelance clients will hurt your schedule, as your clients have to wait for the review results before they can use it. Creating a custom app will enable your client to use it a few seconds after deploying the app to your server.

### 2.) When creating or testing your app for your own store.
![Testers hard at work.](/assets/images/public-vs-custom-5.jpg)
*Testers hard at work. <span>Photo by <a href="https://unsplash.com/@kobuagency?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">KOBU Agency</a> on <a href="https://unsplash.com/s/photos/web-tester?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

Most of the time, I use the apps I develop myself in my own production store. This is for me to understand how my customers feel when they are using my apps. In product management parlance, this is "[eating your own dog food](https://en.wikipedia.org/wiki/Eating_your_own_dog_food){:target="blank"}." 

Eating your own dog food is one thing, but paying for it is on another level of crazy. That is why I create another custom app in parallel to the public app already deployed, installed solely for me. For free, of course.

### 3.) When creating an app for a friend or partner for free or via X-Deal.
![](/assets/images/public-vs-custom-6.jpg)
*<span>Photo by <a href="https://unsplash.com/@joeel56?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Nicole Wolf</a> on <a href="https://unsplash.com/s/photos/developer?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

Sometimes, you want to give someone free access to your app in exchange for something outside Shopify. Maybe you want close friends to use it for immediate and unfiltered feedback. Offering free access in exchange for domain expertise is also fair trade. 

In these particular cases, go with creating a custom app and launch one web instance per merchant.

### 4.) When you need to use the app NOW.
![](/assets/images/public-vs-custom-7.jpg)
*Damn it John, I want that app now! <span>Photo by <a href="https://unsplash.com/@icons8?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Icons8 Team</a> on <a href="https://unsplash.com/s/photos/boss-angry?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

Finally, when anyone needs a feature immediately and when stakes are high, setting up a temporary custom app as a stopgap solution can save your behind. Once the dust has settled, you can always spin and publish up a proper public app for everyone else.

Do you have some use cases that were not covered? Leave your comment below, we love to hear your thoughts!




