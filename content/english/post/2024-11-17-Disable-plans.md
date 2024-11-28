---
title: Disable Viral and internal plans
description: What are viral and internal plans and why should you disabled them
date: '2024-11-27T07:11:06.185Z'
images: 
- images/blog/title-disable-plans.png
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

This is the next part of our mini series called "Admins Essentials" covering all the activities that an Admin should have done at least once or needs to do re-occuring. This time we check out what viral and internal licensing plans are, and why we should disable them 🙂


## The Catchy Introduction: The Danger of the Invisible Licenses

Imagine discovering that half your organization has unknowingly signed up for a free trial of a tool you’re supposed to govern. Sounds like a sci-fi dystopia, right? 

In the world of Power Platform, this dystopia has a name: Viral and Internal Plans. They’re trial licenses designed to empower users but can easily spiral out of control, creating headaches for administrators. Let’s unravel what these plans are, why they’re risky, and—most importantly—how to regain control.

## What are viral and internal plans?

Both viral and internal plans share a noble goal: enabling users to explore Power Platform without friction. But in practice, they can wreak havoc on governance. These trial licenses often bypass traditional oversight mechanisms, leaving administrators in the dark about who’s accessing what—and for how long.

- **Viral Plans**: These are trial licenses granted automatically when a user accesses a Power Platform resource (like a shared app or flow) without having the required license. This "viral" nature comes from its ability to spread within the organization as more users interact with shared resources.

- **Internal Plans**: These are also trial licenses, but they are explicitly initiated by a user, such as when someone signs up for a Power Platform trial through the Microsoft website or admin portal.



Once again we have a classic Shadow IT mechanism with users getting licenses without the admin knowing about this. Once again, I want to give users the opportunity to work with Power Platform, but when I'm responsible for security, I need to know what's going on. And that leads us to the question...

## Why Are They Dangerous?

When licenses are handed out like free candy, it’s easy to lose track of who has what. This can lead to apps and flows relying on trial licenses that suddenly expire—causing disruptions for end-users and leaving admins scrambling for solutions:

- **Lack of Visibility**: Licenses are granted without prior admin approval.
- **Shadow IT**: Users can build critical apps or flows with trial licenses, creating unsupported dependencies.
- **License Sprawl**: These plans muddy the waters when analyzing actual license usage, making budgeting and compliance harder.
- **Security Gaps**: Viral plans might inadvertently grant access to sensitive data or environments.


> when I'm responsible for security, I need to know what's going on

## PowerShell to the rescue

Fortunately, taming this licensing chaos is simpler than you might think. With a few PowerShell commands, you can disable the auto-issuance of these plans and bring licensing back under control. It's, as usual, not the amount of effort you need to put it, but you have to be aware that this is even a thing!

For this we will need the [Microsoft.PowerApps.Administration.PowerShell module](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.112), which means, we will need at least the **Power Platform Administrator** admin role for this.
If you are new to PowerShell, check out this [Beginner's Guide](https://www.michaelroth42.com/post/2024-04-10-getting-started-with-powershell/), or if you need help with modules, [click on this blog](https://www.michaelroth42.com/post/2024-04-16-ise-modules-and-roles-copy/).

You can disable them separately if you want to, yet I recommend to deactivate both. As an Administrator you are still able to grant trial licenses afterwards and you can even switch these plans back on, if you need to. So you don't have to worry that your actions might not be reverseable. They are.

<span style="color:green">##Sign in to the PowerShell module</span>
```
Add-PowerAppsAccount
```

<span style="color:green">##Check the current allowed plans</span>
```
Get-AllowedConsentPlans
```

![I have both plans enabled](/images/Disable_Plans_1.png)

<span style="color:green">##Remove the Internal and Viral plans</span>
```
Remove-AllowedConsentPlans -Types @("Internal", "Viral")
```

![After disabling and checking again, both are gone](/images/Disable_Plans_2.png)

This is a quick and easy fix for this problem. If you need to enable then again, then your code looks pretty similar:

~~~
Add-AllowedConsentPlans -Types @("Internal", "Viral")
~~~

## Conclusion

Once again, a super short blog. It's not about the amount of effort, but that you are aware of this. Power Platform is all about empowerment—but as administrators, it’s our job to balance freedom with responsibility. By understanding the risks of viral and internal plans and taking proactive steps, you can ensure your organization’s Power Platform journey is smooth, secure, and stress-free.

If you want to learn more about plans and how they work, check [Thibualt Joubert's blog about this](https://www.thijoubert.com/2021-07/Control-PowerPlatform-Access/).


If you've heard me talking about Power Platform Governance 101 on an event, watch out for more posts tagged with "Admin's Essentials", that's where I explain all the important things that you need to be aware of ⚠️

Thanks a lot for reading, and if you have comments, questions, or remarks, feel free to contact me on social media. I'm happy to chat and help and learn 😉

Michael on [Bluesky](https://bsky.app/profile/michael42.bsky.social) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)

<br> Thank you for reading!




