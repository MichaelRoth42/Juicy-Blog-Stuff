---
title: Switch on tenant Isolation
description: ""
date: 2022-05-24T16:08:19.024Z
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: true
---

# Switch on tenant isolation

Recently a new (old) Power Platform feature came into preview and it's a huge deal.

I'm talking about cross-tenant isolation (or short tenant isolation). In the past you had to raise a support ticket in the Power Platfom Admin Center to activate tenant isolation and I hardly know any admin who actually did that.

Now you have a handy little switch in your Power Platform Admin Center to switch it on.

{{< image src="images/blog/Tenant_Isolation_4.png" >}}

## Why should you care?

Even if you have a very mature security concept (you have multiple DLP policies in place, external sharing is managed, automatic forwarding is disabled, you have the creation of custom connectors monitored) there is a crucial aspect you need to consider.

With tenant isolation you can block inbound and outbound connections from and to another tenant.

That means without tenant isolation someone can create a flow that connects to another tenant (if you have the credentials).
If you ever worked with guest accounts, service accounts or external contractors, you should consider this.

Here is a demonstration between a flow that works between two tenants:

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

You see, there is the possibility to run flows from in your tenant from a different tenant.

If you work with multiple tenants in your organization you can add tenant rules to create exceptions. You can decide if this exception is only for inbound, for outbound or for both. That gets you a lot of possibilities to customize it to your needs.

## Further ressources

[Enable cross-tenant isolation](https://docs.microsoft.com/power-platform/guidance/adoption/tenant-isolation)

[Power Platform & Tenant isolation: why everyone should have a look at it?](https://www.thijoubert.com/2021-07/PowerPlatform-TenantIsolation/)