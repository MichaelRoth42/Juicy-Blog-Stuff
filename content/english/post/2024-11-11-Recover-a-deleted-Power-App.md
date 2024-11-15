---
title: Recover a deleted Power App
description: How to recover deleted assets in Power Platform using Power Automate and PowerShell. Regardless where they have been stored, you can recover them :)
date: '2024-11-11T07:11:06.185Z'
image: 
- images/blog/title-recover-apps-and-flows.png
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
  - PowerShell
type: regular
draft: false
---

Hey there, this is the start of a mini series called "Admins Essentials" covering all the activities that an Admin should have done at least once or needs to do re-occuring. The posts will be small with detailed step-by-step explanations so everyone will be able to follow along 🙂

## Introduction

Imagine this scenario: A Power Platform administrator, perhaps during a routine cleanup or maintenance task, accidentally deletes a key Power App or a critical automated flow. The impact of this can range from minor inconvenience to severe workflow disruption, depending on what the app or flow was handling. In either case, restoring it quickly is essential. Or a citizen developer accidentally deletes the app, everyone was working on for the last couple of days. Oopsie 😱
Luckily it's usually quick and easy to restore an app or an flow (even in the default environment).

## PowerShell to the rescue

For this we will need the [Microsoft.PowerApps.Administration.PowerShell module](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.112), which means, we will need at least the **Power Platform Administrator** admin role for this.
If you are new to PowerShell, check out this [Beginner's Guide](https://www.michaelroth42.com/post/2024-04-10-getting-started-with-powershell/), or if you need help with modules, [click on this blog](https://www.michaelroth42.com/post/2024-04-16-ise-modules-and-roles-copy/).

We begin with the cmdlet ``Add-PowerAppsAccount``, and wait for the pop-up to sign in with our credentials.

![Connecting our account with the right tenant in PowerShell](/images/RestoreApps_1.png)

Then we get a list of all deleted PowerApps in the dedicated environment. We only need the environment ID for this cmdlet ``Get-AdminDeletedPowerAppsList -EnvironmentName <Environment ID>``

The result is a list of all applications that were deleted during the retention period. 

![The result of the PowerShell cmdlet](/images/RestoreApps_2.png)

And here is a little reminder about the supported retention periods in different environments 😉

![supported retention period in different environments](/images/RestoreApps_3.png)

The last step is to actually recover the app. We will use the cmdlet ``Get-AdminRecoverDeletedPowerApp -EnvironmentName <Environment ID> -AppName <AppName>``

The result is a quick reply with a code (hopefully it's a 200 🤞) like this:

![Result of restoring the application](/images/RestoreApps_4.png)

This is how the restored app looks in the maker studio and it just works like a charm:

![How it looks in the maker studio](/images/RestoreApps_5.png)

![The restored apps works like before](/images/RestoreApps_6.png)

## And what about flows?

If you (or any user) accidentally deleted a Power Automate Flow, things work a bit different. Theoretically you have two options:

1. Use PowerShell to recover flows 
2. Build a flow to recover deleted flows

(you might have guessed it, I'm gonna show you both options)

## PowerShell for Flow recovery

In theory you should use the Get-AdminFlow cmdlet and use it for a skript that lists all flows from a dedicated environment:<br>
``Get-AdminFlow -EnvironmentName <Your-Environment-ID> -IncludeDeleted $true``

Yet the result shows you nothing, not even an empty object. That is a known issue by now (Nov 13th, 2024) and should be fixed at some point.

![No result from the Get-AdminFlow cmdlet](/images/RestoreApps_7.png)

**Flow recovery with PowerShell is not possible at the moment**

## Power Automate for Flow recovery

The [Microsoft documentation](https://learn.microsoft.com/en-us/power-automate/how-tos-restore-deleted-flow) mentions Power Automate to recover deleted flows at first, so we can assume it's the preferred solution.

The idea is simple, you build a flow that lists all flows in an environment, including the deleted ones, then you restore the desired flow based on that list. 

![Straightforward flow design](/images/RestoreApps_8.png)

Yet the devil likes to hide in the details. When you run a flow like this, Power Automate will only show you flows that are stored in a solution. That means, in the last action "Restore Deleted Flow as Admin" you won't be able to select the deleted flows.
There are two things you need to set up in the "List Flos as Admin (V2)" action first:

1. in the advanced settings, include soft-deleted flows as well. Set it to "Yes"
![Select to include soft-deleted flows](/images/RestoreApps_9.png)

2. select the ellipsis and navigate to settings. Turn on the pagination and set the value to 100000
![Switch on pagination](/images/RestoreApps_10.png)

Only now you see all the flows of an environment, regardless of whether the flows are stored in a solution or not. You can also see all deleted flows from the last 21 days.

The flow that you restore will show up in the menu "My flows", yet it will be turned off. Select the ellipsis to turn it back on again and voilá, that's how we recover a flow.

![The restored flow is back and only needs to be switched on again](/images/RestoreApps_11.png)

## Best practice from the real world

When you build this flow the way I build it in this example, it can be problematic. You need to get the output from the "List Flos as Admin (V2)" action and copy/paste it into the "Restore Deleted Flow as Admin" action. 

![manually paste the name into the flow - that sucks](/images/RestoreApps_12.png)

If you want to build it a bit more elegant, you use variables like this:

![A more elegant with variables](/images/RestoreApps_13.png)

Let me walk you through:

1. You add a manual input and type the name of the flow you want to restore 

2. When the name you set as input matches the display name of a flow you have in that environment...

3. ...then this flow will be restored. 

(of course that means you have to know th name of the flow you want to restore)

## Conclusion

That are the possibilities we have right now to restore Power Apps and Power Automate flows. Remember to get the settings right when you want to recover a flow, otherwise it's gonna be frustrating. It's a bit easier for apps in my opinion.

I will update this post, as soon as the PowerShell cmdlet will work again 

Thanks a lot for reading, and if you have comments, questions, or remarks, feel free to contact me on social media. I'm happy to chat and help and learn 😉

Michael on [Bluesky](https://bsky.app/profile/michael42.bsky.social) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)

<br> Thank you for reading!




