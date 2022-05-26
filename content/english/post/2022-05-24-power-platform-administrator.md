---
title: Power Platform Administrator
description: ""
date: '2022-05-24T14:11:06.185Z'
author: "Michael Roth"
tags: 
    - Power Platform
    - Governance
    - Administration
    - Security
type: "regular"
draft: "true"
image: ""
images: ""
---

# Designate Power Platform Administrator

When it comes to administer the Power Platform you want to designate a Power Platform Administrator. This role has the ability to manage everything around the platform at the tenant level, without having as much rights as the Global Administrator.

## Why consider a Power Platform Administrator?

If you want to implement and use the Power Platform in your organization, the administrative effort is quite high at the beginning. Too much for regular IT to do on the side.
Therefore, it is necessary to appoint a Power Platform Admin to take care of all administrative tasks.

## How to assign the role?

You can assign this role in the Microsoft 365 Admin Center:

In the "Users" menu, select "Active users". Then select the user you want to assign the Power Platform Admin role to.

![a picture showing the active users menu in the Microsoft 365 Admin Center](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/PowerPlatformAdmin_0.png)

Select "Manage roles", then "Admin center access" and finally expand the menu by selecting "Show all by category".

![a picture showing the manage roles button in the Microsoft 365 Admin Center](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/PowerPlatformAdmin_01.png)
![a picture showing the manage admin roles menu in the Microsoft 365 Admin Center](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/PowerPlatformAdmin_1.png)

You will find the Power Platform Administrator role with a little infobox, describing the access to Microsoft Dynamics 365, PowerApps, data loss prevention policies, and Power Automate.
Select the box to assign the role.

![a picture showing the Power Platform Administrator role in the Microsoft 365 Admin Center](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/PowerPlatformAdmin_2.png)
![a picture showing the content of the infobox from the Power Platform Administrator role](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/PowerPlatformAdmin_3.png)

>Don't confuse the Power Platform Administrator with with Environment Administrator. The Environment Administrator is the administrator of a certain environment, the Power Platform Administrator ist the administrator of the whole Power Platform in the tenant. I will explain the Environment Administrator in the blog "Environment Strategies".

## Power Platform Admin Center

There are different ways to get to the Power Platform Admin Center (often abbreviated to ppac):

1. In the Microsoft 365 Admin center select "All admin centers" on the left pane and then select "Power Apps" or "Power Automate" to get directed to the Power Platform Admin center.
2. When you're on the [Microsoft Flow Homepage](www.flow.microsoft.com) or in the [Power Apps studio](www.make.powerapps.com), you can select the cogwheel in the upper right corner, then you find the link to the admin center.
3. You can type "aka.ms/ppac" in your browser

Please know that every user with a Dataverse license is able to access the Power Platform Admin Center (through the ways #2 and #3). They can only see the environments they are members of and can only access the resources they are authorized to access.

In the next chapters of the basic category you will find a few settings that are important, since every user with a license is able to access the Power Platform Admin Center.

## Rights of the Power Platform Administrator

|                                                                              | Power Platform Admin |
|------------------------------------------------------------------------------|----------------------|
| **Environments**                                                             |                      |
| Full access                                                                  |           ✅          |
| Create                                                                       |           ✅          |
| Delete                                                                       |           ✅          |
| Backup & restore                                                             |           ✅          |
| Copy                                                                         |           ✅          |
| Ability to exclude access from selected environments (using security groups) |           🛑          |
| **Analytics**                                                                |                      |
| Capacity                                                                     |           ✅          |
| Capacity allocation                                                          |           ✅          |
| Microsoft Dataverse                                                          |           ✅          |
| Power Automate                                                               |           ✅          |
| Power Apps                                                                   |           ✅          |
| **Help & support**                                                           |                      |
| Create and access support requests                                           |           ✅          |
| **Data integration**                                                         |                      |
| Create new project and connection sets                                       |           ✅          |
| **Data gateways**                                                            |                      |
| View gateways                                                                |           ✅          |
| **Data policies**                                                            |                      |
| View and manage tenant policies                                              |           ✅          |
| View and manage tenant policies                                              |           ✅          |
| **Microsoft 365**                                                            |                      |
| Create users                                                                 |           🛑          |
| Add security roles                                                           |           🛑          |
| Add licenses                                                                 |           🛑          |

I welcome comments, remarks and discussions about your experiences with Power Platform Governance, if I forgot something and what I can do better 🙂

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)