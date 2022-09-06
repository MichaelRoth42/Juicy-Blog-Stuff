---
title: Think about limiting environment creation
description: "This blog describes why and how to limit the environment creation in the Power Platform Admin Center"
date: 'Tue, 06 Sep 2022 00:08:51 +0000'
images: 
- images/blog/title-limit-environment-creation.png
author: Michael Roth
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: false
---

# Think about limiting environment creation

By default every user with a Dataverse license can access the Power Platform admin center can create new production and sandbox environments, as well as trial environments.

## Why should we care?

I often advocate to let users work with the tools we give them. Yet the creation of new environments is not necessarily a tool and it affects the whole tenant. Creating lots and lots of new environments with databases can eat up your capacity and impact the performance of the entire tenant. It's not the users' responsibility to think of environments and therefore a setup of Power Platform. That is the work of the low-code strategy team.

Depending on the way we handle our Citizen Developers and Makers we can either leave this setting as it is (everybody can create new environments), or restrict it. For each type of environment (production and trial) we can decide whether every user should be able to create new ones, or if we limit this to specific admins only.
These specific admins are:

- Global Admins
- Dynamics 365 Admins

If we have a Power Platform Admin team that has the capacities to create every new environment for users, this might be a valuable option.
If we don't want to put more work on our admin team and give makers the possibility to work with the tools we give them, we can leave the settings as they are (or check the chapter about environments, where I give an idea on how to automate the environment creation process).

There are a few things to keep in mind regarding security considerations:

- We can think of building an approval process that gives the admin team the possibility to approve or deny the creation of a new environment by a user (check the PowerShell possibilities for that, the links are at the end of this blog).
- Every environment that is created by a user will be shown in the Center of Excellence, so we don't have a unnoticed wildgrowth of environments. Still this can get out of hand rather quickly.
- For every environment that gets created with a database, 1GB of capacity has to be available so take this into consideration when deciding how to use those settings. It is really helpful to talk with the admin team to get a feeling for how much capacity is used.

## Capacity allocations

Per default every environment admin is able to allocate additional capacity to environments. I recommend limiting that to **only specific admins** since the capacity allocation can have a huge impact on the performance of our Power Platform. This way we maintain the overview at our specific Power Platform admin (team). We can create an approval process to allocate capacities to a certain environment, in which an environment admin must specify a business justification. This way we give environment admins room to maneuver without giving up security and overview in our tenant.

## How to change the environment creation settings

In the Power Platform admin center, select the cogwheel in the upper right corner and select **Power Platform settings**.

![a picture showing the cogwheel in the Power Platform admin center](/images/EnvironmentCreation_1.png)

Now we can define, who can create production and sandbox environments, trial environments as well as who can allocate add-on capacities.

![a picture showing the Power Platform settings menu](/images/EnvironmentCreation_2.png)

## Options with PowerShell

We also have the possibilities to limit the creation of environments to admins via [Microsoft Power Apps Administration PowerShell](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.1):

`$settings = @{ DisableEnvironmentCreationByNonAdminUsers = $true }
Set-TenantSettings $settings`

**Attention** for Trial environments we need a separate cmdlet:

`$settings = @{ DisableTrialEnvironmentCreationByNonAdminUsers = $true }
Set-TenantSettings $settings`

---

I welcome comments, remarks and discussions about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Microsoft documentation

[Control who can create and manage environments in the Power Platform admin center](https://docs.microsoft.com/power-platform/admin/control-environment-creation)

[Plan and manage license and capacity allocations](https://docs.microsoft.com/power-platform/guidance/adoption/capacity-and-licenses)

[PowerShell support for Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-powershell)

[Microsoft.PowerApps.Administration.PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powerapps.administration.powershell/?view=pa-ps-latest)

[Microsoft.PowerApps.Administration.PowerShell in the PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.147)
