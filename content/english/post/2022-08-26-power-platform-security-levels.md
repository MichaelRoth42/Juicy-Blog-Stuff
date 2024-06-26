---
title: How to solve a 'can't see the environment' issue in Power Platform - with cheatsheet
description: This blog describes how to solve the issue when users can't see an environment
date: 'Thu, 01 Sep 2022 11:22:51 +0000'
images:
- images/blog/title-path-to-an-environment.png
author: Michael Roth
tags: 
    - Power Platform
    - Governance
    - Administration
    - Security
    - Dataverse
type: regular
draft: false
---

## "But I can't see the environment!"

Are your familiar with that sentence? I hear user complain that they can't see environments, as well as admins that they can't see user in the environments user list.

If you want a user to work on an environment there are three things to consider (depending on the kind of environment, but basically it's like this):

1. Licensing
2. Security groups
3. Security roles

Depending on which of these a user has, they have access up to different stages. I will go through each of these stages and demonstrate the user experience, as well as the admin experience. That gives you the opportunity to determine, what your users need for which scenario. Should or shouldn't they see that environment? After this post you know how to set all components up to be in control.

For our scenario we try to add users to a production/sandbox environment with a database and an added security group. Be aware that different environments work differently, especially the default environment (more on that later).

We have three users:
User A - Isaiah Langer - Microsoft E5 license without the Power Platform Apps

User B - Henrietta Mueller - Microsoft E5 license with the Power Platform Apps included

User C - Joni Sherman - Microsoft E5 license with the Power Platform Apps included and she is part of the Security group "Super Secure"

## Scenario A: No license, no security group, no security role

When we log in as Isaiah Langer we can't see any of the Power Platform products listed under apps on [www.office.com](www.office.com).

![Image that shows all apps of the logged in user. There are no Power Platform apps](/images/SecurityLevels_0.png)

When we directly go to [make.powerapps.com](make.powerapps.com) we only see the default environment (which is called Personal Productivity in my tenant 😉).

![Image that shows that the logged in user has access to the default environment only](/images/SecurityLevels_2.png)

---

As an Administrator we don't see Isaiah in the list of users of our environment and if we try to add him, we get an error message.

![Image that shows a list of all users of the environment. Isaiah Langer is not on that list](/images/SecurityLevels_3.png)
![Image that shows an error message we the admin tries to add the user Isaiah Langer to that environment](/images/SecurityLevels_4.png)

## Scenario B: No security group, no security role

When we log is as Henrietta we can see the Power Platform products Power Apps, Power Automate as well as Power BI on [www.office.com](www.office.com).

![Image that shows all apps of the logged in user. There are all the Power Platform products](/images/SecurityLevels_6.png)

When we go to [make.powerapps.com](make.powerapps.com) we can see the default environment as well as her personal developer environment. That's due to the fact that we gave her the Microsoft Power Apps for Developer license.

![Image that shows that the logged in user has access to the default environment as well as her personal developer environment. The right side of the image shows the Power Platform for Developer license we assigned](/images/SecurityLevels_7.png)

---

As an administrator we can already see Henrietta in the user list of the environment, despite we haven't actively added her yet.

![Image that shows a list of all users of the environment, including Henrietta](/images/SecurityLevels_8.png)

The reason for that is simple:
> every licensed user is automatically added to every environment.

Henrietta is added to the environment, but she isn't part of the security group, nor has she a security role to access any resources within the environment. When we try to assign a security role to her, we get an error message and see what's happening in the background. User get added to an environment, but when the environment has a security group, the user get set on "disabled".

![Image that shows an error message, saying "Failed to assign role 'Basic User': roleFailureDuetoUserIsDisabled"](/images/SecurityLevels_9.png)

Even though users are added automatically by having a license, they can't see the environment until they get a security role. You can't even assign a security role, when they're disabled due to not being in the right security group.

Hint: Sometimes you don't see users in a newly created environment. Usually you can see them after their next log in, when they visit the [maker portal](www.make.powerapps.com)

## Scenario C: No security role

When we log in as Joni, we have the same user experience as with Henrietta. We can see the default environment as well as the development environment, but not the environment which was secured with a security group.

![Image that shows that the logged in user has access to the default environment as well as her personal developer environment](/images/SecurityLevels_10.png)

>Being member of the security group doesn't reveal the environment to you

---

From an administrator point of view, nothing as changed yet either. But when we select her and assign her a security role, we don't get an error message, since she isn't set to "disabled".

![Image that shows that a security role has been assigned to the user Joni Sherman](/images/SecurityLevels_11.png)

Now we are able to assign a security role to Joni. But in order for her to actually see the environment, it is crucial to assign the right security role:

> users need at least environment maker privileges in order to see an environment

And another hint that may save you some time: after you assigned the environment maker role, it usually takes between 20 and 30 minutes until users can see the environment. Sometimes it's necessary for them to log off and on again.

## Conclusion and Diagnostics

Users need an active license, at least the environment maker security role and (if set up) be member of the environment's security group.

In the Power Platform Admin Center you find the option to run diagnostics on user which will show you all this information at a glance.

In an environment, select **user**, then **ellipsis** and then **Run diagnostics**

![Image that shows the user diagnostic dialog](/images/SecurityLevels_13.png)

**Hint:** If you run the diagnostics it forces to sync the Azure Active Directory user information with the environment's Dataverse database. Usually that eliminates all sync errors you may face 💡

---

![CheatSheet: Path to an environment (light mode)](/images/SeeEnv_light.png) _(right.click on the image to open in a new tab for better quality. Or download a light- or dark version in the resource section)_

There we have it, that is the complete way for users to see an environment and interact with it. Do you have similar experiences, do you think this is helpful?

I welcome comments, remarks and discussions about your experiences 🙂

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Useful resources

[Add users to an environment](https://docs.microsoft.com/power-platform/admin/add-users-to-environment)

[Troubleshooting: Common user access issues](https://docs.microsoft.com/power-platform/admin/troubleshooting-user-needs-read-write-access-organization)

[CheatSheet: Path to an environment (light mode)](/images/SeeEnv_light.png)

[CheatSheet: Path to an environment (dark mode)](/images/SeeEnv_dark.png)

---

[Photo in header image by Lili Popper](https://unsplash.com/photos/lu15z1m_KfM?utm_source=unsplash&utm_medium=referral&utm_content=creditShareLink)