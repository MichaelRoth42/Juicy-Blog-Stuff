---
title: Think about a minimal set of environments
description: This blog explains a strategy to start your Power Platform environment strategy
date: '2022-09-26T08:11:06.185Z'
images: 
- images/blog/title-minimal-set-of-environments.png
author: "Michael Roth"
type: regular
draft: false
---

## Environments for Power Platform

Power Platform environments are a great data security layer to separate data, apps, flows and other components of Power Platform solutions. We can think of them as containers we can use to sort our Power Platform assets according to our needs. This way we can target different audiences and purposes while each container serves its own purpose

## Why should we care?

When we sort Power Platform assets for different usages, target audiences of geographical reasons, that helps the users to know when to use what environment. More importantly we can use different security layers with each environment such as data loss prevention policies and security groups. This way we can secure business data and empower users to work with this data in a reasonable way. If your business is operating in different countries with different data security requirements, you can separate the data with environments and secure them each according to the regulations.
Different environments are even the foundation for a good Application Lifecycle Management (ALM) you can find in software development.

## In which environment am I right now?

When you're on [flow.microsoft.com](www.flow.powerapps.com) or [make.powerapps.com](www.make.powerapps.com) you will see your current environment in the upper right corner.

Right now I am in an environment that is called "CoE Demo".
![a picture showing the environment "CoE Demo"](/images/Environment1.png)

If you click on that environment you see a list of all environments you have access to. Maybe you see but one environment that is called "[(default)" in the end. That is your default environment, which everyone has access to per default. Every time a new user gets added,  that user gets added to this default environment as well.
![a picture showing all the environments in my tenant](/images/Environment2.png)

## What kind of environments are there?

### Default Environment

Every organization has a default environment and there is a database connected to that environment. All of your users start creating apps and flows in this environment, which is the reason why most organization use that for personal productivity.

Security: Every user has the security role "Environment Maker" in the default environment. That means they can create new apps, flows or connections. **That role doesn't grant access to data though**.

### Production Environment

These environments are used for long term working scenarios that don't require special features. Microsoft recommends these for the most usecases: *"Production environments are what you should use for any environments on which you depend."*
You can convert your production environment into a sandbox environment anytime. Of course you can convert it back into production as well.

![a picture showing how to convert production environments to sandbox environments](/images/Environment2_convertToSandbox.png)

### Sandbox

Sandbox environments are similar to production environments but you have the possibility to copy, reset it and convert it into a production environment as well (**if your sandbox environment has a database, if it doesn't you don't get those options*).
If you **copy** your environment, you're basically overwriting another already existing environment. Now you can choose if you want to override everything or just customizations and schemas.

![a picture showing the copy menu of environments](/images/Environment2_copy.png)

If you **reset** your environment you set it back to factory settings, deleting everything, including the backups.

![a picture showing the hints of the resetting menu of environments](/images/Environment2_reset.png)

### Trial and Trial (subscription-based)

Trial environments differ from the others, since they have a 30 days expiration limit. After that amount of time they get deleted. They can't be backed up or reset, but they can be converted to a production environment. Therefore these environments are perfect for testing or training purposes. They are limited to one per user, yet you can add additional users to this environment.

If you get a Power Platform trial subscription, you can get a trial (subscriptions-based) environment as well, which can be used for multiple users and includes Office 365 apps. This way you can learn and experiment with Power Platform solutions that include apps and services without having to deploy a demo tenant.
Subscription-based trial environments (sometimes called Admin-trial environments) are tied to the expiration of the subscription and get's deleted when the subscriptions needs to get renewed.

Both environment types don't consume paid capacity.

### Developer environments

Developer environments are dedicated for learning and developing solutions. A user can request a developer environment by subscribing to the [Power Apps Community Plan](https://powerapps.microsoft.com/developerplan/). These environments are strictly for individual use, since it can't be shareed with other users. But we get access to premium connectors and developed flows and apps can be exported from that environment.

## How to build up your strategy

A Power Platform environment strategy depends on your organization size and the strategic goals you want to achieve with Power Platform, yet there are some best practices.

We always have a **default environment** and as I mentioned in the article about the default environment, personal productivity solutions can be developed and used here by every user who has a license.

I suggest to set up a specific environment for **Team- or business unit productivity**. These usecases may be more complex than individual productivity and in the blog about data loss prevention policies I will talk about how the DLPs differ from the default environment.

If we want to encourage our users to learn and get more out of Power Platform and aim for those team productivity solutions, we should set up a **Learning Environment** for makers in which they can learn how to use all tools of Power Platform according to rules, regulations and governance policies we set up in our tenant.

These three environments (you can even think about setting up one Team/BU productivity environment per team or business unit) cover all the usecases around personal or team productivity and usually I recommend to separate these usecases from more critical usecases that aim for a wider audience.

If we have important business productivity or even critical solutions, we need to set up a whole set of environments for these usecases. Each business unit that wants to develop Power Platform solutions for important business cases need their own developer, testing and production environments.

The same is true for business critical solutions.

![a picture showing the described Power Platform environment strategy](/images/EnvironmentStrategy.png)

---

I welcome comments, remarks and discussions about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Useful resources

[PowerApps Community Plan](https://powerapps.microsoft.com/blog/communityplan/)

[Environments overview](https://docs.microsoft.com/en-us/power-platform/admin/environments-overview)

[Defining a Power Platform Environment Strategy](https://docs.microsoft.com/en-us/microsoft-365/community/defining-a-power-platform-environment-strategy)

[Establishing an environment strategy](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/environment-strategy)