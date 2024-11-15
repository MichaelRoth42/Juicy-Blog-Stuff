---
title: Disable Viral and internal plans
description: What are viral and internal plans and why should you disabled them
date: '2024-11-17T07:11:06.185Z'
images: 
- images/blog/title-disable-sharing-with-all.png
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
  - PowerShell
type: regular
draft: true
---

This is the next part of our mini series called "Admins Essentials" covering all the activities that an Admin should have done at least once or needs to do re-occuring. This time we check out what viral and internal licensing plans are, and why we should disable them 🙂


## Introduction - Why "Share with All" in Power Platform is a (Hilariously) Bad Idea

Imagine you’re hosting a cozy house party for your team, only to realize halfway through that you accidentally sent invites to everyone—including random neighbors, delivery drivers, and even a few exes. That’s basically what happens when you hit “Share with all” in Power Platform. 
The group “All” often includes externals, guests, and even some long-lost accounts that are definitely not on the guest list for your app. So, unless you want your app in the hands of every Martha, Dick, and Jane with access to your tenant, it's best to avoid this option!
Go contact your Entra ID team, because almost every organization I know already set up different groups for "all employers", "employers plus guests" or "Just management". You should use groups when distributing applications to a large crowd, but the "Share with all" button is usually way too much.

And before one accidentally overshares apps and the connected data, restrict the possibility by switching off this default option right from the start 😎

## PowerShell to the rescue

For this we will need the [Microsoft.PowerApps.Administration.PowerShell module](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.112), which means, we will need at least the **Power Platform Administrator** admin role for this.
If you are new to PowerShell, check out this [Beginner's Guide](https://www.michaelroth42.com/post/2024-04-10-getting-started-with-powershell/), or if you need help with modules, [click on this blog](https://www.michaelroth42.com/post/2024-04-16-ise-modules-and-roles-copy/).

I would recommend to use PowerShell ISE or Visual Studio Code, because we will need multiple lines of code here.

![The script we need in Powershell ISE](/images/Disable_Sharing_With_All_1.png)

<span style="color:green">##Log into your account</span>
```
Add-PowerAppsAccount
```

![Connecting our account with the right tenant in PowerShell](/images/Restore_Apps_1.png)

<span style="color:green">##Create a variable called "tenantSettings", set it to disable sharing with everyone, then set the tenant settings to the value of the variable</span>

```
$tenantSettings = Get-TennantSettings
$tenantSettings.powerPlatform.powerApps.disableShareWithEveryone = $true
Set-TenantSettings $tenantSettings
```

## Conclusion

That was a super short one, yet it's important that administrators are aware of this and how this works. If you've heard me talking about Power Platform Governance 101 on an event, watch out for more posts tagged with "Admin's Essentials", that's where I explain all the important things that you need to be aware of ⚠️

Thanks a lot for reading, and if you have comments, questions, or remarks, feel free to contact me on social media. I'm happy to chat and help and learn 😉

Michael on [Bluesky](https://bsky.app/profile/michael42.bsky.social) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)

<br> Thank you for reading!




