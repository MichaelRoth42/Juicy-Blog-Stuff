---
title: Understanding Power Platform Architecture
description: Is Power Platform PaaS or SaaS and why should you know? Learn everything about responsibilities and architecture in this blog
date: '2024-04-02T08:11:06.185Z'
images: 
- images/blog/title-architecture.png
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: false
---

Welcome back to the next blog in the ppacAttack series, run by Craig White and me. I have to admit that the topic can feel a bit tough, but believe me, you'll thank me when the next auditor comes around. It’s about Power Platform architecture, Platforms as a service and software as a service (PaaS and SaaS) but also about Pizza, so it can’t be that bad, right? 🍕😎

Okay, I hope you all know the [Pizza-as-a-service](https://www.linkedin.com/pulse/20140730172610-9679881-pizza-as-a-service/) metaphor from [Albert Barron](https://www.linkedin.com/in/albertbarron/) from 20124. It’s a great way to understand the basic difference between systems that are hosted [on-prem](https://pimpyourowndevice.com/community/onpremsucks/) and those that come as some form of online service. Mainly we have Infrastructure as a service (IaaS), Platform as a service (PaaS) and Software as a service (SaaS). They all include different aspects that are managed by Microsoft for you. 
 
 ![Image that shows the difference between IaaS, PaaS and SaaS](/images/IaaSPaaSSaaS.png)

Now, especially you as a Power Platform Administrator should be very aware of the differences between them and should know what exactly that means. What is hosted and provided by you and your organization and what comes from Microsoft. 

Why should you know all of this? 🤷‍♂️

I have recently accompanied many Power Platform administrators during security audits. IT security deals very closely with these models, so you should at least know what your responsibilities are and where they stop.

I usually use this overview
 
![Image that shows layers and responsibilities of security scoping](/images/SecurityScoping_1.png)

## Is Power Platform PaaS or SaaS?

When we look at the Power Platform and the capabilities to create apps, flows and service without worrying about all the structure underneath, it’s pretty clear that it’s a Platform as a service (PaaS). Now Power Apps, Power Automate and all the other service inside the Platform are a bit different though. They’re often described as a Software as a service (SaaS), since user don’t need to manage the application. But what about the maker? They pretty much manage the application, and they also have the possibility to manage the network controls as well (more on that later). So I guess it’s a solid hybrid, depending on from which point of view you look at it. 
 
![Image that shows different aspects being true, to whether Power Platform or dedicated services are considered PaaS or SaaS](/images/SaaSorPaaS.png)

Now what does that mean for you as a Power Platform Administrator, especially since I mentioned security audits? Those audits usually take all the different layers into consideration that are mentioned under Security Scoping. And they want you to answer if you manage those and where the documentation is (people who follow me will realize that I don’t stop talking about documentation and this is another good reason why 😉).

Now let’s investigate the bits and part that may or may not fall into your area of responsibility.

![Image that shows layers and responsibilities of security scoping, now with a red frame around the parts considered in this blog](/images/SecurityScoping_2.png)
 
## The Power Platform Admin part
We will focus on the right side of the overview and only look at the PaaS and the SaaS part and before you start to worry, the Power Platform Admin is not alone responsible for all these layers. It’s teamwork 🙂
 
![An Aragorn meme about teamwork](/images/Teamwork.png)

Let's start at the most basic level that you are responsible for in a PaaS model and work our way all the way up:

**-	Network controls <br>**
If you are a Power Platform Administrator, you have a shared responsibility with Microsoft to take care about the network controls. That basically means the connectivity to the internet and which URLs can and can’t be used. For that Microsoft provides Power Platform URLs and IP address ranges that you need to allow in order for Power Platform to work. Additionally, we have the Virtual Network support for Power Platform in preview right now. This allows us to run the Power Platform service on virtual machines, which is pretty neat. Both aspects count under “network controls” when it comes to responsibility. It’s best to be familiar with those concepts, document how it’s done in your organization, so you can be prepared for any audit. Remember, you don’t necessarily have to explain what happens, if you just got it properly documented 💡<br>

**-	Applications <br>**
Microsoft provides you with developer tools to create and manage your own applications. The Power Apps Maker Studio for example. You are not responsible for how those tools work, but that they work and whether you want to provide your users access to those tools, or not. Document which services you use and which user have access under which conditions.<br>

**-	Identity & directory infrastructure <br>**
Once again, a shared responsibility, Microsoft provides you with Entra AD, yet you (or your organization) is responsible for the tenant’s identity security configuration inside Entra AD. Who gets a guest account, how are they managed, who is responsible for deleting orphaned accounts, and so on. Most probably this is not your responsibility as a Power Platform Admin, yet you should document who’s it is. When you’re responsible for the Platform, you need to know who takes care about this. <br>

**-	Accounts & Identities <br>**
Which accounts and identities have access to the Platform and the different environments that you’ve come up with? Does that sound familiar? Good, this is about Security Groups that you (hopefully) use to manage access and rights in your Power Platform 😁
Again, write it down, how this works in your organization and you will be good to go.<br>

**-	Devices (mobiles and PCs)<br>**
This usually is taken care of, by whoever works with Microsoft Intune in your organization. If you don’t use it at all, you probably have someone who is in charge of handing out devices and making sure, that those devices are safe and secured. That is the person who can help you document how devices are secured in your organization. <br>

**-	Information and data <br>**
This is a classic “it depends” question. Responsibility for data security is usually shared between the user (often you find something like a “Information Classification” concept to label certain data) and the ones providing the data storage. Within the Microsoft universe that can be OneDrive, SharePoint, Fabric, Azure Datalake or Dataverse. Depending on where the data is stored, different administrators are responsible for this. Additionally, the access to different data sources is managed through DLPs (Data Loss Prevention Policies). This is the moment when you should know exactly where you have documented your DLPs 😉<br>

![Craig says header](/images/CraigSays.png)
*Your shared responsibility isn’t just with Microsoft but with other areas of your business too. The above points therefore underline how critical these relationships are to building & maintaining a healthy ecosystem. Administration across the Microsoft stack is a team effort between any combination of the following (or similar) roles:*


- Power Platform admins
- Microsoft 365 admins
- Azure admins
- Security leads/engineers
- Architecture/Technical Design Authority
- Data leads/engineers
- Governance & Compliance/GDPR experts <br>

*Having a shared understanding across the board will not only help with those invasive security audits, but allow you to embrace a cross-functional working culture that’ll be critical for ongoing success. This is as much about knowing how their areas impact yours, as it is the other way around. Make sure you have the tools in place to foster transparent communications between all involved.*


## The Low-Code Maker part
If you are someone who develops apps and flows and other services with the Power Platform, only a few of these parts are important to you. When you’re developing and deploying a Power App, you are responsible for at least the “Accounts & Identities” part. 

Even when you’re not an Environment Admin, you can decide who you share your app with. It is your responsibility to do this to the best of your knowledge and belief. And, of course, to document it. Not with individual names, but with security groups. Talk to your local Admin if you’re unsure how to do this, if he follows this blog, they should be pretty awesome and capable 🫶

## The whole picture
It is difficult to sum everything up in just one picture, but in the end it’s about knowing who is responsible for what part. Especially in a good governance and security documentation, the important part is that you have it written down somewhere. Security and governance always consist of many different layers that hold up IT security together. Even if there are aspects that aren’t absolutely bullet proof (we all have those aspects in our architecture), it’s crucial to be aware of that and to document that. So we don’t get caught by surprise. 
Once again, it’s a team effort and to start the conversation between Platform owners, admins and everyone in between, I use some kind of overview to make clear, who is responsible for what. Like this one:

![Image that shows an overview over how Power Platform, M365 and Azure are built upon each other, and which admin is responsible for what part](/images/Tenant_Overview.png)
 
This is also very beneficial if you start to have a conversation with your Power Platform Environment Administrators and start documenting what’s their responsibility. You did that already, didn’t you? 😉

As usual, thanks for reading, if you have questions, comments, and stories to share, find us on social media and let’s talk. We can all learn from each other 😊


Michael on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)
Craig on [Twitter](https://twitter.com/platformspower) and [LinkedIn](https://www.linkedin.com/in/craig-white-/)

<br> Thank you for reading!




