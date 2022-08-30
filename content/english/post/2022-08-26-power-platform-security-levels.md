---
title: Power Platform Security Levels
description: This blog describes the different threshold level of security you need to know about, if you want to give (or deny) users access to data in an environment
date: 'Mon, 15 Aug 2022 11:22:51 +0000'
images:
- images/blog/title-Power-Governance-Setting-Scene_2.png
author: Michael Roth
tags: 
    - Power Platform
    - Governance
    - Administration
    - Security
    - Dataverse
type: regular
draft: true
---

## Path to working in an environment

If you want a user to work on an environment you need three steps (depending on the kind of environment, but basically it's like this):

License
Security group
Security role

Depending on which of these a user has, they have access up to different stages. I will go through each of these stages and demonstrate the user experience, as well as the admin experience. That gives you the opportunity to determine, what your users need for which scenario. Should or shouldn't they see that environment? After this post you know how to set all components up to be in control.

We have four users:
User A - Isaiah Langer - Microsoft E5 license without the Power Platform Apps 

User B - Henrietta Mueller - Microsoft E5 license with the Power Platform Apps included

User C - Joni Sherman - Microsoft E5 license with the Power Platform Apps included and she is part of the Security group "Super Secure"

User D - Mini Me - Microsoft E5 license with the Power Platform Apps included and standalone Power Apps per user license and he is part of the Security group "Super Secure"

## Scenario A: No license

When we log in as Isaiah Langer we can't see any of the Power Platform icons listed under apps on www.office.com. But of course users have the opportunity to get to Power Automate or Power Apps through other apps, foremost SharePoint and Microsoft Teams. 

## Scenario B: Security group

## Scenario C: Security role

Which security feature governs which access right?

## Useful resources

[]()

---

[Photo in header image by Viktor Bystrov](https://unsplash.com/photos/tXIpcZhVKiQ)