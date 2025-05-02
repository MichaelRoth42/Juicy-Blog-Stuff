---
title: How to unmanage an environment?
description: Learn how to convert a managed Power Platform environment back to unmanaged using PowerShell. 
date: '2025-04-30T07:11:06.185Z'
images: 
- images/blog/title-how-to-unmanage.png
author: "Michael Roth"
tags:
  - Tech
  - PowerPlatform
  - Governance
  - Security
  - PowerShell
type: regular
draft: false
---

# From Managed to Unmanaged – A Quick PowerShell Trick

Sometimes it takes just one smart question to inspire a blog post.  
Shoutout to my customer (you know who you are 😉) who recently asked:  
*“How can I turn a managed environment into an unmanaged one?”*

Now, I genuinely like **Managed Environments**. They bring a lot of structure, guardrails, and visibility to the Power Platform—plus, features like solution checker enforcement, maker welcome content, and better ALM integration are pretty awesome.

**But**—and here’s the big but—**they require a premium license for every user**. And let’s be real, that’s a tough sell in many organizations.

So, back to the question: Can you *unmanage* a managed environment?  
**Yes, you can.** And surprise: it works beautifully with **PowerShell**.

## 🛠 What you need

Before we begin:
- Make sure you’ve installed the [**Microsoft.PowerApps.Administration.PowerShell**](https://learn.microsoft.com/en-us/powershell/module/microsoft.powerapps.administration.powershell/?view=pa-ps-latest) module.
- Log in using an account that has **environment admin or tenant admin permissions**.
(The cmdlet `Add-PowerAppsAccount` will open a login prompt)

If you’ve got that covered, here's how it works:

### Step 1: Create a custom object in a variable

```powershell
$IWantOut = [pscustomobject]@{ protectionlevel = "Basic" }
```
as you can see, my variable is called "I want out", but you can name it whatever you like. But be warned:

>The human brain is amazing. It functions 24/7 from the day we’re born and only stops when you’re naming a variable or speaking to someone attractive. 🤓😂

![This is how it looks](/images/unmanagedEnvironment_1.png)

### Step 2: Run this cmdlet

```powershell
Set-AdminPowerAppEnvironmentGovernanceConfiguration 
  -EnvironmentName "<your-environment-name>" 
  -UpdatedGovernanceConfiguration $IWantOut
```
Replace `<your-environment-name>` with the name of your managed environment. **And with name, I mean Environment ID** (don't you love how often name and ID get confused in the documentation?)

![After running the script successfully](/images/unmanagedEnvironment_2.png)

That’s it! This changes the governance configuration and effectively removes the managed environment status.

If you've never worked with custom objects in PowerShell, don't worry—I’ve got you covered. I wrote a blog post all about it [Let's create custom objects](https://www.michaelroth42.com/post/2024-05-01-lets-create-custom-objects/) that walks you through the basics.

Because sometimes governance means knowing when to simplify, and today, that means switching from managed to unmanaged. And if you haven't found [the official documentation from Microsoft](https://learn.microsoft.com/en-us/power-platform/admin/managed-environment-enable#disable-managed-environments-using-powershell) (like I didn't), I also got a link for you 😅

Thanks again to my customer for the great question—and for reminding me that the best blog topics come from the real world.

## The End
I welcome comments, remarks and discussions about your experiences with Power Platform Governance.

Find me on [LinkedIn](https://www.linkedin.com/in/michaelroth42/) an [BlueSky](https://bsky.app/profile/michael42.bsky.social)