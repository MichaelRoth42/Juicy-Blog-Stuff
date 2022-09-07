---
title: Designate Power Platform Administrator
description: "This blog is a guide why and how to designate specific Power Platform administrator and what they actually have to do"
date: '2022-08-29T08:11:06.185Z'
images: 
- images/blog/title-power-platform-administrator.png
author: Michael Roth
tags: 
    - Power Platform
    - Governance
    - Administration
    - Security
type: regular
draft: false
---

## Designate Power Platform Administrator

When it comes to administering Power Platform you want to designate a **Power Platform Administrator**. This role has the ability to manage everything around the platform at tenant level, without having as much rights as the Global Administrator.

## Why consider a Power Platform Administrator?

If we want to implement and use Power Platform in an organization, the administrative effort is quite high at the beginning and too much for regular IT to do on the side.

Microsoft advises to come up even with a whole team, which depends on the size of your organization, but may be worth considering. Let's check the most important tasks on a Power Platform Admin's list:

- Establish and maintain an environment strategy
- Set up Data Loss Prevention (DLP) policies
- Manage security groups and assign users
- Take care about capacity and licensing
- Make data available to makers
- Handle integration and migration
- Handle security
- Monitor makers efforts

A designated admin will increase the chance of your makers working in a well structured environment with clear rules. That leads to fast learning makers, which makes their projects develop faster, being more efficient and ultimately them make better decisions.

## How to assign the role?

You can assign this role in the **Microsoft 365 Admin Center**:

In the **Users** menu, select **Active users**. Then select the user you want to assign the Power Platform Admin role to.

![a picture showing the active users menu in the Microsoft 365 Admin Center](/images/PowerPlatformAdmin_0.png)

Select **Manage roles**, then **Admin center access** and finally expand the menu by selecting **Show all by category**.

![a picture showing the manage roles button in the Microsoft 365 Admin Center](/images/PowerPlatformAdmin_01.png)

![a picture showing the manage admin roles menu in the Microsoft 365 Admin Center](/images/PowerPlatformAdmin_1.png)

You will find the Power Platform Administrator role with a little infobox, describing the access to Microsoft Dynamics 365, Power Apps, Data Loss Prevention policies, and Power Automate.

Select the box to assign the role.

![a picture showing the Power Platform Administrator role in the Microsoft 365 Admin Center](/images/PowerPlatformAdmin_2.png)

![a picture showing the content of the infobox from the Power Platform Administrator role](/images/PowerPlatformAdmin_3.png)

> Don't confuse the Power Platform Administrator with with Environment Administrator. The Environment Administrator is the administrator of a certain environment, the Power Platform Administrator ist the administrator of the whole Power Platform in the tenant. I will explain the Environment Administrator in the blog **Environment Strategies**.

## Power Platform Admin Center

There are different ways to get to the Power Platform Admin Center (often abbreviated to ppac):

1. In the Microsoft 365 Admin center select **All admin centers** on the left pane and then select **Power Apps** or **Power Automate** to get directed to the Power Platform Admin center.
2. When you're on the [Power Automate Homepage](https://flow.microsoft.com) or in the [Power Apps studio](https://make.powerapps.com), you can select the cogwheel in the upper right corner, then you find the link to the Admin center.
3. You can type `aka.ms/ppac` in your browser

Please know that every user with a Dataverse license is able to access the Power Platform Admin Center (through the ways #2 and #3). They can only see the environments they are members of and can only access the resources they are authorized to access.

In the next chapters of the basic category you will find a few settings that are important, since every user with a license is able to access the Power Platform Admin Center.

## Rights of the Power Platform Administrator

This is the part where the documentation might be a bit misleading. Checking the table below it seems as if the Power Platform Administrator can't use security groups, add security roles, licenses or create new users. Basically it says, the role can create environments and the whole infrastructure but relies on another role to manage Power Platform user.

But don't be fooled, that's not entirely true, otherwise the role would be very limited. The Power Platform Admin can:
- Create new security groups
- assign user to security groups
- assign security roles
- edit security roles

The table below is somewhat correct, since the Power Platform Admin can't create security groups and assign them in the Microsoft 365 Admin Center, but has to use the Azure Portal instead 😉

The Power Platform Admin however can not:
- Create new users
- add licenses

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

## Switch on Tenant Isolation

The Power Platform Administrator has the ability to switch on tenant isolation. That is to block inbound and outbound connections from and to another tenant. If it's not switched on, there can be a connection created to our tenant (e.g. a flow), that wouldn't be blocked by a data loss prevention policy. If you have guest accounts, service accounts or external contractors working on your tenant, consider this safety measure.

In the Power Platform Admin Center select **Policies** and the **Tenant isolation (preview)**. Switch the toggle to **On** and select Save.

![a picture showing the Power Platform admin center and the Policies menu](/images/Tenant_Isolation0.png)

If we work with multiple tenants in our organization we can add tenant rules to create exceptions. We can decide if this exception is only for inbound, for outbound or for both. That gets us a lot of possibilities to customize it to our needs.

If you want an example, [Thibault Joubert has a great blog](https://www.thijoubert.com/2021-07/PowerPlatform-TenantIsolation/) in which he describes how it works.

## Low-code strategy team

Since we're on it we should think about something else regarding the Power Platform Admin. Every Administrator will thank you, if their task list is based on the organizational strategy and goals. They implement measures to reach the goals and they prefer to do it in a structured way (remember me saying that Administrator hate to put out fires unexpectedly?).

The way Power Platform fits into our strategical goals, our IT landscape and in our culture needs to be decided by key decision makers who know the big picture. Don't let your admins come up with something like that, it's not their job. Gather a team from business, IT, and management side to think about cross-organizational collaboration and how a low-code platform will improve it.

[I welcome comments, remarks and discussions](https://twitter.com/MichaelRoth42/status/1564508722508009472?s=20&t=2qvzxiSj03RvPNT6OqpnWw) about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Useful resources

[Microsoft Power Platform Best Practices - Roles and Responsibilities](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/roles)

[Admin and governance best practices (tasklist)](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/admin-best-practices)

[Designate the Microsoft Power Platform admin role](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/pp-admin)

[Enable cross-tenant isolation](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/tenant-isolation)

---

[Photo in header image by Matty Adame](https://unsplash.com/photos/nLUb9GThIcg)