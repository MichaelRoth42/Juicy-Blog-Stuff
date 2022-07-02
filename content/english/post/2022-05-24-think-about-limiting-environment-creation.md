---
title: Think about limiting environment creation
description: ""
date: '2022-05-24T15:30:38.565Z'
images: 
- images/blog/title-calling-connector.png
author: Michael Roth
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: true
---

# Think about limiting environment creation

By default every user with a Dataverse license who can access the Power Platform admin center can create new production and sandbox environments, as well as trial environments.

## Why should we care?

I often advocate to let the user work with the tools we gave them. Yet the creation of new environments is not necessarily a tool and it affects the whole tenant. Creating lots and lots of new environments with databases can eat up our capacity and impact the performance of the whole tenant. It's not the users responsibility to think of environment and therefore a setup of Power Platform. That is the work of the Low-Code strategy team.

Depending on the way we handle our Citizen Developer and Maker we can either leave this setting as it is (everybody can create new environments), or restrict it. For each type of environment (production and trial) we can decide whether every user should be able to create new ones, or only specific admins.
These specific admins are:

- Global admins
- Dynamics 365 admins
If we have a Power Platform Admin team that has the capacities to create every new environment for the user, this might be a valuable option.
If we don't want to put more work on our admin team and give the maker the possibility to work with the tools we gave them, we can leave the settings as they are (or check the chapter about environments, where I give an idea on how to automate the environment creation process).

If we have security considerations, there are a few things to keep in mind:

- we can think of building an approval process that gives the admin team the possibility to approve or deny the creation of a new environment by a user (check the PowerShell possibilities for that, the links are at the end of this blog).
- every environment that is created by a user will be shown in the Center of Excellence, so we don't have a unnoticed wildgrowth of environments. Still this can get out of hand rather quickly.
- For every environment that gets created with a database, 1GB of capacity has to be available so take this into consideration when deciding how to use those settings. It is really helpful to talk with the admin team to get a feeling for how much capacity is used.

## Capacity allocations

Per default every environment admin is able to allocate additional capacity to environments.I recommend limiting that to "only specific admins" since the capacity allocation can have a huge impact on the performance of our Power Platform. This way we maintain the overview at our specific Power Platform admin (team). We can create an approval process to allocate capacities to a certain environment, in which an environment admin must specify a business justification. This way we give environment admins room to maneuver without giving up security and clarity in our tenant.

## How to change the environment creation settings

In the Power Platform admin center, select the cogwheel in the upper right corner and select "Power Platform settings".

![a picture showing the cogwheel in the Power Platform admin center](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/EnvironmentCreation_1.png)

Now we can define, who can create production and sandbox environments, trial environments as well as who can allocate add-on capacities.

![a picture showing the Power Platform settings menu](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/EnvironmentCreation_2.png)

## Options with PowerShell

We also have the possibilities to limit the creation of environments to admins via PowerShell:

`$settings = @{ DisableEnvironmentCreationByNonAdminUsers = $true }
Set-TenantSettings $settings`

**Attention** for Trial environments we need a separate cmdlet:

`$settings = @{ DisableTrialEnvironmentCreationByNonAdminUsers = $true }
Set-TenantSettings $settings`

---

I welcome comments, remarks and discussions about your experiences with Power Platform Governance, if I forgot something and what I can do better 🙂

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Microsoft documentation

[Control who can create and manage environments in the Power Platform admin center](https://docs.microsoft.com/power-platform/admin/control-environment-creation)

[Plan and manage license and capacity allocations](https://docs.microsoft.com/power-platform/guidance/adoption/capacity-and-licenses)

[PowerShell support for Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-powershell)

[Microsoft.PowerApps.Administration.PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powerapps.administration.powershell/?view=pa-ps-latest)

[Microsoft.PowerApps.Administration.PowerShell in the PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.147)