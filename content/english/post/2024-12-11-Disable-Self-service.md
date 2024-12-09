---
title: Disable Self purchase services
description: Learn what self-service purchases are, why you don't want them and how to switch them off
date: '2024-12-11T07:11:06.185Z'
images: 
- images/blog/title-disable-self-service-2.png
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

Welcome back to this mini blog post series called "Admin's Essentials", in which we talk about those tasks that every Administrator has to do once or twice or at least, be aware about it.

Let’s talk about why self-service purchases can disrupt your governance strategy and how to turn off this feature to ensure you stay in control of your tenant.

## The Catchy Introduction: Shut up and take my money

Ah, self-service purchase—the idea that users can buy what they need when they need it, skipping the red tape of traditional procurement. Sounds great in theory, right? But for admins, it’s more like giving your entire office team a corporate credit card without telling finance. Sure, some purchases might be justified, but others? Chaos.

This is literally a "shut up and take my money" moment. 

Self-service purchasing allows users to directly buy Microsoft products and services—like Power BI Pro or Power Platform licenses—without needing admin approval. While this may seem convenient, it comes with significant risks:

- **Budget Chaos**: Individual purchases make it hard for organizations to track and manage software budgets effectively.
- **Security Risks**: IT has no oversight of who owns or uses the purchased licenses, potentially leading to compliance issues.
- **Governance Breakdown**: Users could end up with conflicting or unmanaged configurations, creating a governance headache.
- **Support Nightmares**: Who do they call when it breaks? Spoiler alert: It’s you, the admin.

By disabling self-service purchasing, you align license management with your governance model, ensuring a streamlined process for approvals, tracking, and support.

But wait, what products actually allow self-service purchases? Do I even need to bother at all? Let's find out:

## PowerShell to the rescue

For this we will need the [MScommerce PowerShell module](https://www.powershellgallery.com/packages/MSCommerce/2.3), which means, we will need the **Billing Admin** or **Global Admin** role for this.
If you are new to PowerShell, check out this [Beginner's Guide](https://www.michaelroth42.com/post/2024-04-10-getting-started-with-powershell/), or if you need help with modules, [click on this blog](https://www.michaelroth42.com/post/2024-04-16-ise-modules-and-roles-copy/).

If you haven't used this module before, first of all you need to install it:

```Install-Module -Name MSCommerce```

After that is finished you need to connect to it:

```Connect-MSCommerce```

![After connecting you're asked to sign in with your credentials](/images/Disable_Selfservice_1.png)

Then we can get a list of all products that allow self-service purchases with the cmdlet:

```Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase```

![All Microsoft products that allow self-service purchases at the moment](/images/Disable_Selfservice_2.png)

The list grows over time, as we can see that Microsoft 365 Copilot is a fairly new entry. You can also see that I have disabled a few of these products already. On the right hand side you can see the Policy value, which is disabled. 

You have three options to disable the self-service purchase of these products:

1. Disable them with their product ID

When you know the product ID (or if you look it up), you can use the following cmdlet (and add the right product ID. In this example I've used the one for Power BI Pro):

```Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0H9MP -Value "Disabled"```

2. Disable them with their actual product name

If you don't know the ID from the top of your head or don't want to bother, just use this cmdlet and type in the product name (at the place that now says 'Power BI Pro'):

~~~
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where { $_.ProductName -match 'Power BI Pro‘ }
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
~~~

3. Disable all at once

~~~
$Products = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
foreach ($Product in $Products){
    Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $Product.ProductID -Enabled $false
}
~~~

Here is an example where I used the cmdlet where I type the product name and disable it this way. You can see the output, where I get the information with the product name, the ID, the policy ID and the value, set to "disabled".

![Success message of disabling the self-service purchase of Power BI Pro](/images/Disable_Selfservice_3.png)

## Conclusion

Disabling self-service purchases is not about limiting creativity or access to tools—it’s about fostering a structured, collaborative environment where IT and users work together effectively. When users bypass governance, they often face delays, unsupported configurations, or even security risks. By taking control of self-service purchases, administrators can ensure that users still have access to the tools they need but in a way that aligns with organizational policies and best practices.

Remember, governance isn’t about saying "no" to innovation; it’s about saying "yes" in a way that’s safe, efficient, and sustainable. With just a few PowerShell commands, you can take a proactive step toward creating a more organized and secure Microsoft 365 environment.

---

If you've heard me talking about Power Platform Governance 101 on an event, watch out for more posts tagged with "Admin's Essentials", that's where I explain all the important things that you need to be aware of ⚠️

Thanks a lot for reading, and if you have comments, questions, or remarks, feel free to contact me on social media. I'm happy to chat and help and learn 😉

Michael on [Bluesky](https://bsky.app/profile/michael42.bsky.social) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)

<br> Thank you for reading!