---
title: Disable self-service
description: "This blog describes why and how to disable the self service features for Power Platform in your tenant"
date: '2022-05-24T16:36:45.435Z'
images: 
- images/blog/title-disable-self-service.png
author: Michael Roth
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: true
---

# Disable self-service purchase

User can purchase Power Platform licenses online and use them in their organization without consulting with IT or an admin.

## Why should we care?

This can lead to a shadow IT like behavior. In a later blog I will recommend to train and support users before they get access to all the Power Platform environments in an organization in order to help them grow their skills bit by bit.

If users are denied a license, they still have the possibility to buy them on their own. That means, even if we decided to not use Power Platform in our organization, there is the possibility that users will create Power Platform solutions on their own (this does not work for guest users).

With their email address and their Azure Active Directory credentials they can sign in to the self-service portals of Power Platform and buy licenses. They then get access to a limited view of the Microsoft 365 admin center and can assign those licenses, but only to to users in the same Azure AD tenant.

As an admin however we have the possibility to see all self-service purchases in our Microsoft 365 admin center.

In the admin center, select **Billing** and then **Your products**

![a picture showing the Microsoft 365 admin center](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/Self-service_1.png)

On the right side of the screen we find that there are already filters in place. Select the filter option and then the Self-service account type to see all products purchased by the self-service.

![a picture showing the product filer in the Microsoft 365 admin center](https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/Self-service_2.png)

If we decided to not use Power Platform in our organization, we may want to inform our users, why we decided this way. As an additional measure we can disable the self-service purchase with the **MSCommerce PowerShell** module.

After installing the module we can run this little script to disable the self-service possibility for users in our tenant per product. We need to run it for every product we want to exclude from the self-service:

```
Import-Module -Name MSCommerce Connect-MSCommerce //sign-in with your global or billing administrator account when prompted//
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase |
where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -Policy
```


I welcome comments, remarks and discussions about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Further ressources

[MSCommerce PowerShell module in the PowerShell Gallery](https://www.powershellgallery.com/packages/MSCommerce/1.7)

[Use AllowSelfServicePurchase for the MSCommerce PowerShell module](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell?view=o365-worldwide)

[Self-service purchase documentation](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell?view=o365-worldwide)
