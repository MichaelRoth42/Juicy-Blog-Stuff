---
title: Take care about your default environment
description: "Things you should consider to set up in your default environment before you start to roll out a dedicated Power Platform environment strategy"
date: '2022-09-19T08:11:06.185Z'
images: 
- images/blog/title-take-care-about-your-default-environment.png
author: "Michael Roth"
tags: 
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: false
---

The default environment is created automatically for each tenant and every user in that tenant got access to it. It's created in the region closest to the default region of the Azure AD tenant and it comes without a database, unless you provision Dataverse to it. Therefor every user who signs up to Power Apps or gets a license assigned is added the Maker role.

## Why should we care?

The default environment is different from all the other kind of environments:

- It can't be deleted.
- It can't be backed up.
- It can't be restored.
- user who open the app [maker studio](www.make.powerapps.com) or [Power Automate](www.flow.microsoft.com) will end up in the default environment automatically
- Flows which are being created from a SharePoint list will be stored in the default environment
- Customized Forms for SharePoint will be stored in the default environment

In conclusion there are two main characteristics about the default environment:

1. Every user who got a license has got access
2. It's difficult to manage

**hint!**
User can access the maker studio (make.powerapps.com or flow.microsoft.com) even without a license. They can build apps but they can’t publish it. Yet they can run it in playmode and if you haven’t blocked any connectors, flows and other functionalities within this app will actually run. Even though the users don’t have a license.

Therefore it is important for you to know a few best practices and take care about your default environment.

## Best Practices

### Rename the default environment

Microsoft intends to use the default environment for any personal productivity usecases. It's the place for every Power Platform solution that only affects the own user account. Therefore the recommondation is, to rename it to make that clear. The most common name is "Personal Productivity". The default naming is *name of your tenant* (default) and you can rename it in the [Power Platform Admin Center](aka.ms/ppac).

Select *Environments*, then select your default environment. In the default menu, select *Edit*, choose a new name and select *Save*

![a picture showing the environment menu in the Power Platform Admin Center](/images/RenameDefEnv.png)

This way all users get an indication that this environment is meant for personal productivity and not for critical usecases or solutions that affect more than the own account.

### Set up a data loss prevention policy

Since every user has access to the default environment and even without a license flows can be triggered, it makes sense to set up a data loss prevention policy (short: DLP). You don't want important and critical usecases be build in the default environment due to the special characteristics of it, so we want to allow connectors of all the Microsoft 365 services our user
have access to. Yet you want to exclude Dataverse and block all connectors from 3rd parties. You will end up with the following connectors per category:

**Business** (exclude all the apps users don't have access to)

- SharePoint
- OneDrive for Business
- Approvals
- Defender for Cloud Apps
- Excel Online (Business)
- Notifications
- Microsoft Kaizala
- Dynamics 365 Customer Voice
- Office 365 Outlook
- Office 365 Groups
- Office 365 Groups Mails
- Office 365 Users
- OneNote (Business)
- Planner
- Power Apps Notification
- Power Apps Notification V2
- Power BI
- Shifts for Microsoft Teams
- Skype for Business Online
- Microsoft Teams
- Microsoft To-Do (Business)
- Yammer

**Non-business**

- Microsoft Dataverse (legacy)
- Microsoft Dataverse

**Blocked**

- *all the other connectors*

**Important!**
There are constantly new connectors added, so we make sure to set the default group for new connectors to *Blocked*. This way every new connector automatically gets sorted into the blocked category and our DLP stays always up to date.

In the Power Platform Admin Center, we select *Data policies*, in the *Prebuild connectors* menu we select the cog wheel in the upper right corner. We select *Blocked* and then *Apply*.

![a picture showing the prebuild connectors menu in the Power Platform Admin Center](/images/RenameDefEnv_2.png)

### Change SharePoint custom forms

You can change where SharePoint custom forms are stored instead of the default environment with the PowerShell Administrator module.

`Get-AdminPowerAppSharepointFormEnvironment`gets you the name of the current environment that is used for custom SharePoint forms
`Set-AdminPowerAppSharepointFormEnvironment –EnvironmentName 'EnvironmentName'` let's you set a different than the default environment.

There you have it, with this we should have built a well equipped default environment to roll out Power Platform in our organization.

---

I welcome comments, remarks and discussions about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Useful resources

[The default environment](https://docs.microsoft.com/en-us/power-platform/admin/powerapps-powershell#designate-sharepoint-custom-form-environment)

[Defining a Power Platform Environment Strategy](https://docs.microsoft.com/en-us/microsoft-365/community/defining-a-power-platform-environment-strategy)

[PowerShell support for Power Apps](https://docs.microsoft.com/en-us/power-platform/admin/powerapps-powershell#designate-sharepoint-custom-form-environment)

[Get started using the Power Apps admin module](https://docs.microsoft.com/en-us/powershell/powerapps/get-started-powerapps-admin?view=pa-ps-latest)

---

[Photo in header image by Sven Mieke](https://unsplash.com/photos/jO6vBWX9h9Y)