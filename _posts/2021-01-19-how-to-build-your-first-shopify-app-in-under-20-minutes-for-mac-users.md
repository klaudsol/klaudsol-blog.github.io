---
layout: post
title:  "How To Build Your First Shopify App In Under 20 Minutes -  For Mac Users"
categories: shopify
published: false
---
![GraphQL](https://mcusercontent.com/2258b1142d581e51c131c3e0e/images/03c35c6b-ec03-4df7-88b5-64b0acc4de95.png "How to Access Shopify Data From Your App")

Are you an experienced developer, and suddenly you have a brilliant Shopify app idea that you are itching to breathe life to? 

Do you have an impossible deadline, set by your client, boss, (or yourself, you maniac), and you just need to get things done?

Did you just accept a Shopify app freelance job, and you have absolutely no idea how to create a Shopify app? (I admire your courage).

This guide is specifically for YOU. We shall create and set up your first WORKING Shopify App, without the pain and struggle, in 20 minutes or less. 

Unlike other tutorials where you build from ground zero up, we start with a perfectly working app. You can modify it afterwards to fit your specific requirements.

Without further ado, let’s get shit done.

# Prerequisites

This guide are written under the following assumptions and prerequisites:

### You are an experienced developer familiar with the following tech stack:
* Node.js 
* ReactJS
* GraphQL

If you think you need further experience in any of the mentioned stack, you may find it helpful to read separate tutorials on these topics. You may faithfully follow the instructions in this guide first, then proceed to study the technologies after your Shopify App is up and running.

### You are using macOS Catalina or later.

It might work on earlier versions of macOS, however I have not tested it, so proceed at your own risk;

Many of the commands will work on Ubuntu or other Linux distributions, albeit with a handful of adjustments and tweaking. Things always work with Linux, given enough adjustments, tweaking, and loads of time.

Watch out for the Ubuntu version of this guide!

### You have installed the latest Node and NPM on your machine.

You can use homebrew to install Node. See https://treehouse.github.io/installation-guides/mac/node-mac.html for more instructions.

# Quick start - create your first Shopify app (development environment)

### Create a Shopify partner account

Go to https://partners.shopify.com/signup and create a FREE Shopify partner account.

It may be also apt to check your email account now to verify your account, to get that out of our list.

### Create a new app inside your Shopify partner account

1. Go to Apps > Create App
2. Choose whether you want to create a Custom App or a Public App.
    * Custom App - if you are building for one specific shop only. Best for freelance, client-based projects, and commissioned work.
    * Public App - if you are building for everyone to install and download. Best for posting it on the Shopify App Store and earn for every download. For the sake of this tutorial, let’s create a Public App.

3. For the General Settings:

   * App Name - Name it whatever you want it to be. IMPORTANT! Make it completely clear that this is the DEVELOPMENT application e.g. My First App (DEV).  We will need a separate application for the PRODUCTION version later, so we better get the naming correct to avoid confusion. It will be named similar to your development application, without the (DEV) marker e.g. My First App

   * App URL - this can be https://localhost/ (will be automatically updated later)

   * Whitelisted redirection URL(s) - This can be https://localhost/ (will be automatically updated later)

 4. Press Create App

 * Once done, it will take you to the App Dashboard. IMPORTANT! Take note of the API Key and API Secret Key. We will need that in later steps.
