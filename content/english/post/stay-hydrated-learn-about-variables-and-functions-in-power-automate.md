---
title: 'Stay hydrated - Learn about Variables and Functions in Power Automate'
date: Sun, 17 Jan 2021 14:30:50 +0000
draft: false
tags: ['Blog', 'M 365', 'Power Automate']
---

Recently I was looking for super easy mini flows to implement with Power Automate. I’m talking about one or two step flows to make it comfortable for beginners to start with process automation.  

My first flow was a tea timer. Just a button that would send me a notification 3min later. Super easy, yet it brought me into the world of workflows. 

A general notification use case can be helpful for a lot of people: remember to water the plants, remember to order groceries, remember to drink enough water, and so on. [Luise Freese pointed out](https://twitter.com/LuiseFreese/status/1350432942036815877?s=20), that she used to have a flow to remind her to drink a sufficient amount of water per day and that Vivek, aka [That API guy](https://twitter.com/that_API_guy) built a pretty neat flow for that already. 

So I looked into [his tutorial](https://thatapiguy.tech/2019/08/26/stay-hydrated-%f0%9f%92%a7%f0%9f%92%a7%f0%9f%92%a7-using-microsoft-teams-flow-and-powerbi/) and tried to rebuild that. With every flow you build you learn something new.  

And so did I. I learned about some functions I never used before: 

*   Variables in a flow (how to use the intFunction in a variable and what is an integer value?) 
*   Post a choice of options as the Flow bot to a user 
*   Switch 

I don’t want to describe Viveks flow here, if you’re interested, [visit his blog](https://thatapiguy.tech/2019/08/26/stay-hydrated-%f0%9f%92%a7%f0%9f%92%a7%f0%9f%92%a7-using-microsoft-teams-flow-and-powerbi/) and try to build it for yourself. I just want to focus on the things I didn’t fully understand at the beginning. 

I’m not experienced with functions, variables and everything that revolves around that. I never learned about them, so I think it’s one of the major challenges for business users without an IT background to dig into this. In this flow I’m working with two variables that contain integer values and I want to explain both of them, because once you get it, you’ll discover a whole new world of possibilities. 

[via GIPHY](https://giphy.com/gifs/disney-aladdin-llipschitz-yyvSeRGVj4C64)

#### **Variables in this flow** 

There are two variables in this flow and both work with the intFunction. You’ll need to understand what’s a variable and how the intFunction sets this variable. Let’s dive into this. 

![](https://gezeitenbrand.de/wp-content/uploads/image-2.png)

**What's a variable?** 

First you need to understand, what a variable is. In programming you can work with variables and constants. A variable is a container that stores specific information or values. The content may vary, depending on what you want it to be. But the program itself will work with that variable, regardless of the information inside it.  

Here’s an example: 

If you want an app to show you how many hours of work you have left for the day, you need to calculate the amount of hours from NOW (the moment your looking at the app) until the end of the workday. Since you don’t want to give the app the information about the current time, everytime you look at it, the app works with a variable. This variable contains a function, most likely called something like currentTime or something. Whatever the current time actually is, the app works and calculates with that value. 

The opposite of a variable is a constant. The value of a constant doesn’t change. You define it and that’s it.  

Variable = container that stores interchangeable values depending on the function inside that variable 

Constant = a fixed value 

The good thing is, that you can create multiple of these containers. In fact, as many as you like. Remember to give them a proper name (in order to see, what they contain without looking into it) and define what the variable should contain and you’re good to go.  

**_What's_****_ an integer value_****_?_** 

uFor this flow it’s also helpful to learn, what an integer value is or what the intFunction does, because this is the content that is going to be in our variable (remember, you want that variable container to store a value. You’re going to define that value with an integer value). 

An integer value is a whole number that can be positive, negative or zero. That’s it. The intFunction converts a string (a set of characters), to a whole number. And do you know what’s way easier to do with whole numbers than with text? That’s right, calculating.  

In order for our flow to work properly, you want to be reminded to drink enough water during the day. But you want it to only remind you during the workday. Otherwise, you’d wake up to multiple messages in Teams to remind you to drink sufficiently (Because the flow is set to remind you EVERY hour). So, you want to limit the reminders to a certain timeframe.  

That means, that you have to let the flow check, whether the current time is within your working hours. The first two steps get the current time and convert the time into a desired time zone. The current time usually consist of the values year, month, day, hour, minute and second. But you want to see, if the current hour is in between 9am and 5pm (an example).  

What you’re looking for is: IF the current hour is greater than 9 AND smaller than 17, then the flow is allowed to remind me.  

So you have to get the hour from the current time. And you want the hour as a whole number value, with which the app can calculate further (computers can calculate with more values than whole numbers of course, but for now we’re working with it).  

And here you have the intFunction, extracting the hour from the current time and translate it into a whole number format for further usage: 

```
int(formatDateTime(body('Convert_time_zone'),'hh')) 
```

![](https://gezeitenbrand.de/wp-content/uploads/image-4.png)

Here is it within some context: 

*   I initialized a variable 
*   Named it “Working hour” 
*   It contains a whole number (type is integer) 
*   The value is set to be the hour in the current time 

The condition is the IF-statement. If the hour is greater than 9 AND is less than or equal to 17, the flow is allowed to run through.  

#### **What else can you do with the intFunction?**

Now let’s have a look at another, pretty clever use of a variable which is set with an intFunction.   

Here you have a variable that shall contain the amount of water that you drank. The type is Integer again, because you want to work with that value later on.  But do you see that there is no value set yet? That is because you’ve initialized the variable, without actually setting it (to set a value means, to give it a value). 

![](https://gezeitenbrand.de/wp-content/uploads/image-3.png)

You are going to define the value later on in the flow.  

You give the user a range of options to choose from. The “Post a choice of options as the Flow bot to a user” action for Teams creates an adaptive card. You can choose what the options with are. 

![](https://gezeitenbrand.de/wp-content/uploads/image-6.png)

Depending on what the user chooses, you want the flow to set the variable “Amount of Water” to a certain value: 

💧 = 100ml 

💧💧 = 200ml 

💧💧💧 = 300ml 

That is what the switch action does:  

![](https://gezeitenbrand.de/wp-content/uploads/image-5.png)

If you wanted to achieve this possibility without the switch action, you’d have to build nested if conditions, which, let’s face it, is a pain in the a\*\* ✌ 

What you see here is a beautiful use of the variable and explains that the value of it is interchangeable. With initializing a variable, you just create a box, and you can fill it with whatever you want. If you want to fill your box, you can use the Set variable action. I just talked about variables of a certain type. There are so many more types and useful functions and possibilities out there I still need to learn.  

I'd love to know if that was helpful to you, let me know in the comments/[on twitter](https://twitter.com/Gezeitenbrand). 

Maybe you have an idea on how to use variables and the intFunction in your flow journey. 

🙂