---
title: Tenant Isolation
description: This blog is going to describe what tenant isolation is and how you activate in on your tenant
date: '2022-05-03T07:43:31.000Z'
images:
    - images/blog/Tenant_Isolation_title.png
author: Michael Roth
tags:
    - Power Platform
type: regular
---
# Tenant Isolation

Recently a new (old) Power Platform feature came into preview and it's a huge deal.

I'm talking about cross-tenant isolation (or short tenant isolation). In the past you had to raise a support ticket in the Power Platfom Admin Center to activate tenant isolation and I hardly know any admin who actually did that.

Now you have a handy little switch in your Power Platform Admin Center to switch it on.

{{< image src="images/blog/Tenant_Isolation_4.png" >}}

But wait, why should you care? What is cross-tenant isolation anyway?

Basically you can block inbound and outbound connections from and to another tenant.

That means you can create a flow that connects to another tenant, if you have the credentials (anyone ever worked with customer who created a guest account?)

Let me show you, what I did to demonstrate this:

I have two tenants:
**ITPtestlab** and **MichaelRoth42**

I'm happily working on my **MichaelRoth42** tenant and come up with a cool flow idea.

{{< image src="images/blog/Tenant_Isolation_1.png" >}}

Everytime a new file get's created in the **ITPtestlab** tenant (and I choose OneDrive to keep in simple) I want to get a notification in my **MichaelRoth42** tenant. Just to demonstrate, that I can create a flow between two tenants, despite both user accounts don't have access to the other tenant.

So, my trigger is OneDrive - When a file is created. I then select the ellipsis and add another connection. I log in with the credentials from the **ITPtestlab** tenant and that's it. A new connection is done.

{{< image src="images/blog/Tenant_Isolation_2.png" >}}

I then get a Microsoft Teams message on my **MichaelRoth42** tenant.

So I create a new file on the **ITPtestlab** tenant and see what happens in Teams on the **MichaelRoth42** tenant:

{{< image src="images/blog/Tenant_Isolation_3.png" >}}

new file is created

{{< image src="images/blog/Tenant_Isolation_5.png" >}}

the flow run successful!

{{< image src="images/blog/Tenant_Isolation_6.png" >}}

If that is not scary I don't know what is.

If you work with multiple tenants in your organization you can add tenant rules to create exceptions. You can decide if this exception is only for inbound, for outbound or for both. That gets you a lot of possibilities to customize it to your needs.

If you want all the details how this works and why, check out Thibault's blog [Power Platform & Tenant isolation: why everyone should have a look at it?](https://www.thijoubert.com/2021-07/PowerPlatform-TenantIsolation/) he explains it pretty straight forward.
