# Why we need Lvl. 50 content for the Power Platform

There is much beginner-friendly material out there explaining how to start with the Power Platform. There is material of any kind describing to you functions, flows, connectors, and how to create your first app, or flow, or dashboard, or even your first bot. This Lvl. 100 content is a great starting point to get going with the Power Platform.

But in real life, not as many people can experiment with building their solutions as we'd like to.

Even with Level 100 content, we overwhelm users. Most people don’t start with www.make.powerapps.com and ‘hello world”, but with wondering about licenses and begging their IT departments to be allowed to play around with Power Platform tools. There is a gap between what we think what they could do and what they really can do. 

It is time to lower those barriers and make it easier for them to get started. 

# How do those barriers look like?

There are many different things that keep users from starting with the Power Platform. Most people who feel want to start, do so at their workplace. There are few users who actually start out from their private accounts, therefor I want to focus on business user. That doesn't mean that the solutions I'm going to describe don't apply for private user as well. 
Let's have a look at possible barriers user face day to day when it comes to the Power Platform:

## You don't know if you have a license
Quite often user have no idea, whether they have the right license to start, or not. And most user don't have access to the Microsoft 365 admin center to check their licenses either. But you can simply check if you license includes Power Platform apps by yourself. Just go to www.office.com and sign in with your work account. Then click on *all apps* and check, if you can find Power Automate, Power Apps, Power Virtual Agent or Power BI.
If you can find them, you do have a license. If you can't find them, that could mean, that your license includes those apps but the IT decided to limit your access or you don't have the right license. Since most license include at least a limited access to the Power Platform, most likely it's due to corporate policy that the IT limited your access. 

## You don't get the licences/access
Since most organizations have E3 or E5 licenses (and bot give you limited access to the Power Platform), it's most likely, that somebody in your organization decided to limit your access to the apps. Quite often there are several reasons for that:

- Lack of information
Let's face it, most people in classic IT departments have a lot of things to do. And learning a whole new stack of software that's build around automation is usually not the highest priority. If IT people want to automate tasks, they already have their tools, like PowerShell, Logik Apps or simply a coding language. They don't have the need for a low-/no-code solution to learn. And most of them don't see, why the business has the need to do that. Many people simply struggle to understand the why and understand the usecase. And in order to empower the business, you need to learn it yourself first. But you don't learn it, if you don't know why you should in the first place.

- Insecurity about usage
From lack of information how and why to use the Power Platform comes insecurity about this whole thing work and how the different solutions interact with each other. The job of the IT is it, to make everything run smoothly. The last thing you need is a user who's starting interacting with your perfectly running environment, right? If you don't know how something works, you'll have a hard time giving permissions to others. Because you can't help out in an emergency. And you don't see the necessity in the first place.

- Fear of breaking something / data leakage
From insecurity about usage comes the fear that the user may break a perfectly running system. Most IT people know about/have created an infinite loop while learning how to code. You don't want user to accidentally create something like this in your production environment. 
Additionally there is the fear of data leakage. A lot of flows use interaction with social media platforms as example for automation. Accidentally tweeting the biggest company secrets, and doing it automatically, doesn't sound very enticing. The idea that the user is being able to perform tasks automatically, without thinking of it, makes people quite nervous. 

## You don't have the time or opportunity 
You have a lot of things to do in your regular job. Do you have sparetime to dig into something like the Power Platform? Most of us are working crazy hours anyway and learning something new can be exhausting and often feels like an additional task. Even if it provides a simple method to create, automate or analyse data, thus making your daily work easier, it can be a lot. 

> I have no time to sharpen my axe! I am very busy trying to cut trees 

## Organization is still on prem

If your organization is still on prem, that sounds like a show stopper, but in fact in isnt'. You do have the possibility to get your hands on the Power Platform, if you want to. 


All those reasons usually come from an (old-fashioned) organizational culture in which there is a gap between the IT- and the business departments. There is no collaboration but instead a climate of working against each other. 
"the IT puts obstacles in my way and thus makes my daily work much more difficult"
"The user is constantly coming up with requests or problems that we need to fix because they don't understand how our system works"
Does that sound familiar? 
Limiting user access to IT system seems to be the easiest way to fix this issue. But this results in 
- leaving the user ignorant and thus ensuring that users will always do things wrong. 
- only IT people using the Power Platform, leaving the question why user need access to it after all.
- learning content that leaves the user clueless how to start, since they don't have access at all.

In the end, this will only deepen the gap between IT and business and lead to frustration on all sides. This undermines the idea of empower every person and every organization in the first place.

--> We need to explain the business need to IT and BDM
--> We need to build up experience on user side to enhace arguments and discuss on eye level.

--> ultimately that will help to unify IT and business and lower the culture of trust issues.

# How does the solution look like?

Microsoft 365 has a very handy initiative called Developer Program. You can learn anything about it at [Welcome to the Microsoft 365 Developer Program](https://docs.microsoft.com/en-us/office/developer-program/microsoft-365-developer-program#:~:text=Join%20the%20Microsoft%20365%20Developer%20Program%201%20Go,form%3A%20Contact%20Email%20Country%2FRegion%20Company%20Weitere%20Artikel...%20)

Basically it let's you set up a tenant for test and developing purposes. You can deploy test user, build solutions for Microsoft Teams, SharePoint Framework, SharePoint Add-ins and so on. 
This tenant comes with a Microsoft 365 E5 Plan so that you have any possibility to experiment. 

## What you need
All you need is any kind of Microsoft account. Maybe your personal or your work account, both work fine. With that you can join the Microsoft 365 Developer Program. 
Once you've done that you can [set up a Microsoft 365 Developer Subscription](https://docs.microsoft.com/en-us/office/developer-program/microsoft-365-developer-program-get-started). That means, that you're creating a subscription with a E5 licence on the developer tenant. With the log in data from that subscription you can sign in to www.office.com at any time and you will find your developer account.

## Whats next?
You may want to check the dashboard in the [Microsoft 365 Dev Center](https://developer.microsoft.com/en-us/microsoft-365/profile). There you can deploy some sample data packs in order to work properly in your tenant. You can deploy:
- users (16 fictionous users with licenses, mailboxes and even photos).
- Mail & Events (mails and calendar events for your users).
- SharePoint (up to 7 templates of team and communication sites).

Especially if you want to try out the Power Platform these sample packages come in very handy. If you want to build flows or apps for users, having actual user data is very helpful. 


## Wait, there's a hook, isn't it?
Yip, of course there is. Actually there are two:
1. The developer tenant will only be active for 90 days (don't worry, you can extend it).
2. Since you have a Microsoft 365 E5 license, there are some limitation when it comes to Power Platform.

There are just few limitations, but you should know what those are. With the Power Apps license for Microsoft 365 you can't
- access on-premise data or use premium or custom connectors
- you can't create new Trial or Production environments
- you just have access to Microsoft Dataverse with certain apps

Again, these restrictions are not that comprehensive, but if they affect the exact aspects you want to try, you need to know that beforehand.

Luckily there are two other possibilities to rise your dev tenant potential. You can use your log in credential from your developer tenant to sign up for on the two following plan:

[**Power Apps Plan Trial**](https://docs.microsoft.com/en-us/powerapps/maker/signup-for-powerapps) gives you Power per user plan for 30 days. This is meant for trying out Power Apps, Dataverse, and Power Automate. Once your trial expires, you can purchase a plan. If you are already using Power Apps with Office 365 or Dynamics 365, this is the right plan to try out the premium functionalities of Power Apps, which are available with Power Apps Per User Plan.

[**Power Apps Community Plan**](https://docs.microsoft.com/en-us/powerapps/maker/dev-community-plan#:~:text=Both%20Power%20Apps%20Plan%20Trial%20and%20Power%20Apps,your%20trial%20expires,%20you%20can%20purchase%20a%20plan.) gives you access to Power Apps premium functionalities, Dataverse, and Power Automate for individual use. This plan is primarily meant for learning purposes or creating business solutions to be distributed for Microsoft AppSource. This plan is perpetually available, but only for learning and building your skills on Power Apps, Dataverse, and Power Automate.

# Conclusion

If you want to learn how automation works within the Microsoft universe and you want the full experience of the Power Platform (Power Automate, Power Apps, Power BI and Power Virtual Agent, including premium connectors, accessing on-premise data and use Dataverse) the combination of a developer tenant with a Power Apps Community plan is the best way to get you going.

You are independet from your organization, you can try out everything you like and you don't need to be afraid to break anything. 
You can build up knowledge and confidence and will be able to talk to your coworkers from IT on a different level, maybe you can even adress some concerns about setting up the Power Platform in your organization. 

I hope this overview was helpful for you 🙂

If you'd like to share your experiences, you will find me on twitter anytime at [@Gezeitenbanrd](https://twitter.com/Gezeitenbrand). 


