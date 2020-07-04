---
layout: post
title:  "How to Sell Apps via the Shopify App Store"
categories: shopify graphql
---

![How to Sell Apps via the Shopify App Store](/assets/images/how-to-sell-apps-via-the-shopify-app-store.png)
*<span>Photo by <a href="https://unsplash.com/@sharonmccutcheon?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Sharon McCutcheon</a> on <a href="https://unsplash.com/s/photos/cash?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

> This is an introduction to the 3-part series on How to Sell Apps via the Shopify App Store. It's time to cash in. 

Who doesn't want to earn extra income? I know I do!

You embraced the pain and pleasure of developing a Shopify app, no matter how some bits can be pretty challenging and excruciating. 

You lost plenty of hair during hair pulls, trying to debug that damn code that won't freaking work. 

You struggled with your internet connection from hell. 

You want to throw your noisy underpowered laptop to the floor many times, before remembering that's all you got and decided you'll just smash it to bits later when you are rich.

**And now you're done**. Sweet sweet victory.

**It's time to cash in.**

Unfortunately, it is not that straightforward. Finishing your app in your local development is just the beginning.

Selling apps over the Shopify app store can involve multiple requirements. It can be really tricky especially to beginners. 

However, once published and selling (Note: the "selling" bit is important), you will be rewarded with **monthly recurring revenue**. 

You will open up a can of beer, place your feet on your table, and quietly enjoy your triumph. I tell you it will be all worth it. 

Fear not, I shall guide you on how to sell your app via the Shopify App store with this 3-part series.

This will serve as our map on our journey. We will explore each part in detail in succeeding posts.

Let's begin.

## 0.) First and foremost, finish your app

![](/assets/images/how-to-sell-apps-via-the-shopify-app-store-1.png)
*Work work work! <span>Photo by <a href="https://unsplash.com/@mimithian?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Mimi Thian</a> on <a href="https://unsplash.com/s/photos/developer-asian-working?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*


This might come as super obvious, but it really needs stating. You can't sell an app if you are not finished. 

For those who has not even started yet, a good starting point is our [free guide to creating a new Shopify app](https://landing.klaudsol.com/shopify-app-in-20-minutes){:target="blank"}. 

**Important** --- This guide takes you to setting up your first working Shopify app *template* to help you get to speed --- no more, no less. 

To create **YOUR OWN**  Shopify app, you will need your time, effort, and magic to create what you have in mind, and actually build it.

For those in the middle of it and plowing your way through with all your might, congratulations! Remember you're closer than you think.

For those getting more and more frustrated with their app, always remember the WHY. Always remember why you started developing in the first place.

Is it because you wanted to provide more money for your kid's tuition fee?  

Is it because you wanted to save up for that Disney cruise?

Is it because you wanted to help your parents in their poor financial condition?

Always go back to answering WHY, and your journey will be easier.



## 1.) Ensure that your app has code for billing

![](/assets/images/how-to-sell-apps-via-the-shopify-app-store-2.png)
*Don't forge the billing code! <span>Photo by <a href="https://unsplash.com/@cgower?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Christopher Gower</a> on <a href="https://unsplash.com/s/photos/code?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

This will seem as a surprise especially for beginners. If you do not involve code for billing, your app will be free. 

You do not want your pain and struggle to be free of charge.

Many developers, including myself, initially expected that the Shopify App Store will take care of the pricing and charging, and will be independent of your app. With Shopify, this is not the case. 

You must code the billing code.


You can code your app to charge [recurringly as a subscription](https://shopify.dev/docs/admin-api/graphql/reference/mutation/appsubscriptioncreate){:target="blank"}, or as a [one-time payment](https://shopify.dev/docs/admin-api/graphql/reference/mutation/apppurchaseonetimecreate){:target="blank"}. My goal is **monthly recurring revenue**, so I go with subscription.

We shall discuss this further, inclusive of sample code, on a future post.

## 2.) Host your app

![](/assets/images/how-to-sell-apps-via-the-shopify-app-store-3.png)
*This probably is how AWS servers look like, but I'm not really sure. <span>Photo by <a href="https://unsplash.com/@wocintechchat?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Christina @ wocintechchat.com</a> on <a href="https://unsplash.com/s/photos/servers?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>*

You need to choose a *reliable* host for your app. You need to consider that your app may, one day, be a huge success, and your app will be used by thousands, ten thousands, and probably millions of Shopify merchants. 

You need your app to be highly available, accessible 24/7 all around the world with minimal downtime. DevOps skills here will be very useful.

You want your hosting to be *affordable* on small usage (for example, around 10 faithful merchants), but also *elastic* enough to handle increase of usage by the tens of thousands in the future.

The [free guide](https://landing.klaudsol.com/shopify-app-in-20-minutes){:target="blank"} recommends [Heroku](https://dashboard.heroku.com/){:target="blank"} as it is 1.) supported out-of-the-box by [Shopfy CLI](https://www.shopify.com.ph/partners/blog/cli-tool){:target="blank"}, it is 2.) easy, and it is 3.) free (**to an extent** --- when thousands actual users come, free won't be able to cut it any longer.).

However, for production-grade hosting, I use [Amazon Web Services](https://aws.amazon.com/){:target="blank"}. It is more than anything a personal choice since my skillsets and experience favor AWS.

In future posts I shall discuss how to host your Shopify app in an AWS EC2 instance.


## 3.) Submit your app for review

![Shopify App Listing Review](/assets/images/shopify-app-listing-review.png)

Once you got the billing code and hosting nailed, you shall then submit your app for review, which in itself is a whole new adventure.

In fairness to Shopify, they really wanted each app to be of tiptop shape and quality so that merchants will get the most out of the Shopify experience. 

This part shall be tedious and demanding (especially if you are itching to generate income), so better prepare your sword and shields, knights. 

In a (probably lengthy) future post, we shall go step-by-step on what it takes to get your Shopify app submitted and approved.

So there you have it, ladies and gentleman. Our adventure map went longer than I had in mind. My next post will be on how to add billing code to your Shopify app.

