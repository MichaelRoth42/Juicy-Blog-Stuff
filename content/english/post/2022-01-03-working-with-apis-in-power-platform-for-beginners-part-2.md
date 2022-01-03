---
title: Working with Custom Connectors in Power Platform for beginners
description: In this post I'm going to explain how to call an API with a custom connector and how to use it in Power Automate
date: '2022-01-03T11:44:44.060Z'
image: "images/blog/title-calling-connector.png"
author: Michael Roth
tags: 
- Power Automate
- Power Platform
- Citizen Developer
type: regular
draft: true
---

# Working with Custom Connectors in Power Platform for beginners

Prologue: This is the second part of the blog [Working with APIs in Power Platform for beginners](https://www.michaelroth42.com/post/working-with-apis-in-power-platform-for-beginners/). If you haven't read it I recommend to head over there to give it a try.
In this blog I want to do exactly the same thing as before: I'm going to call an API with Power Automate but instead of a http request, I'm going to use a custom connector this time. If you want to learn how to build your first custom connector and whats the difference between a hhtps request and a custom connector, this post is for you.

## Custom Connector vs HTTPS request - When to use what?

First of all: a custom connector and a https request generally do the exact same thing. They both call an endpoint of a specific api to get data back.

Since this is a blog for beginner, I won't got into the very details of custom connectors and http requests, yet there is a straight forward explanation for when to use a custom connector instead of a http request:

If more people than just you should be able to use that API call, it makes sense to use a custom connector, because you can easily share it within your tenant.

If the API call you have in mind will be used more than once (in different flows or apps), you might consider creating a custom connector.

So, let's build one right now, shall we? 👏

## Build a custom connector

Since this is part two of my mini series "working with APIs" I'm using the same scenario and api as last time. I use an open API to get the number of the day from a website called MathTOOLs. I will post this number in a Microsoft Teams channel afterwards.

First of all, navigate to your [Power Automate dashboard](www.flow.microsoft.com). Select "Data" and then "Custom connectors". If you already have some, they will be listed here, if not this page is empty. Select "+ New custom connector" in the upper right corner and then "Create from blank".

Now you are in the menu to create your own custom connector. At the top of the page you can see the necessary steps in a navigation:
1. General
2. Security
3. Definition
4. Code (Preview)
5. Test


## 1. General
On the first page is only one mandatory field to fill out. We need to give a Host for our custom connector (but I strongly recommend to fill out the Description as well. Especially when you want to share it, give your colleagues an idea of what your custom connector does 😉). Now you might think, that's the endpoint, like in the previous blog, but it's not. The endpoint is connected to a certain method (GET, PUT, POST, PATCH, DELETE) and since we haven't defined our method yet, this is something else. The host is a part of the URL, usually the documentation will tell you.
In this case, it's **api.math.tools**

You can also upload a nice icon for you connector (which I love, obviously), just make sure that the file is .png or .jpg and smaller than 1MB.

You don't need to fill out the rest. We will look into that at a another blog of this series. For now we're good and we can click on "Security" either in the lower right corner or in the navigation at the top of the page.

## 2. Security
Since we use an open API we don't need to fill out anything here 😊

## 3. Definition
Now things are getting interesting, since we're defining the other parameters here. For this example, we just want to create an action that gets us the number of the day.
Start by selecting "+ New action" on the right hand side.

Once again, only one mandatory field, yet I recommend to fill out the Summary and the Description as well. 
Summary: This will be the name of the action of your custom connector
Description: Gives colleagues a good idea of what it does
Operation ID: This is going to be the string, which is used in the operation. Keep it simple, I guess.

After that information is provided it's time for our request. Select "+ Import from sample" and the next menu should look familiar to you. Here we can choose the **method** as well as the **URL**.
In this case the method is: **GET**, the URL is **https://api.math.tools/numbers/nod**
(We provided the same information at the last part, where we needed to give those to the https request, remember?). When we're done, select "Import" to finish this step.

Now it's time to actually create the connector. Select "Create connector" in the upper right corner and keep your fingers crossed 🤞🤞🤞

Usually you get a success notification ✅ above the upper navigation.

## 4. Code (Preview)
Once again, no work for us here, so we skip this part 😊

## 5. Test
There is one last task for us to finish our custom connector. We need to create a new connection. Select "+ New connection". 
There should appear a connection with the name of your connector in the "Selected connection" field.

Now we just need to test the connector. Select "Test operation" and wait for the response.

If you did everything right you should get a status 200 response. This is a good thing 🙂

Congratulations, you just created your very own custom connector. Now let's take this baby for a test drive in Power Automate, shall we? 😎

## Use your custom connector in Power Automate

