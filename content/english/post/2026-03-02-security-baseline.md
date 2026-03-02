---
title: Minimum Security Baseline
description: A minimum security baseline isn't about blocking everything. Learn how to build simple Data Policies that are contextual, and enforceable without creating chaos
date: '2026-03-02T07:00:00.000Z'
images: 
- images/blog/title-part3-security-baseline.png
author: "Michael Roth"
tags:
  - PowerPlatform
  - Administration
  - Governance
  - Security
  - Microsoft
  - GovSeries
type: regular
draft: true
---

# Minimum Security Baseline

## Why "Minimum" Is the Hardest Part

When admins start thinking about security, the instinct is always to add more. More policies, more restrictions, more controls. It feels safer. It feels thorough. It feels like you are doing your job.

But in Power Platform governance, more is almost never better. More policies create confusion. More restrictions create friction. More controls create a system that nobody understands, not even the person who built it (trust me, I've been there 😅).

The minimum security baseline is not about doing less work. It is about doing the right work. It is about creating a system that is predictable, understandable, and enforceable. A system where makers know what is allowed and why. A system where violations are clear signals, not constant noise.

This is harder than it sounds. Because "minimum" requires you to make choices. It requires you to decide what actually matters and let go of the rest. And that takes more thought than just blocking everything that makes you nervous.

## The Foundation: Data Policies (Not DLP)

Microsoft is moving away from calling these "DLP policies" and toward the term "Data Policies." That is a good shift, because "Data Loss Prevention" was always too narrow. These policies do more than prevent data loss, they govern how connectors can be used, what actions are allowed, and how data flows between systems. Above that there was constant confusion, whether we talked about M365 DLPs, or Azure DLPs and why are they all called DLPs, when they target different systems? 

But the core model has not changed. You still work with three categories:

**Business:** Connectors in this group can communicate with each other. An app using SharePoint can also use SQL Server if both are in Business. Data can flow freely within this group.

**Non-Business:** Connectors in this group can also communicate with each other, but not with anything in Business. You might put social media connectors, external APIs, or experimental tools here. They work together, but they are isolated from your core business data.

**Blocked:** Connectors here cannot be used at all. They do not appear in the maker experience. They are not available for selection.

This three-tier model is enough for most organizations. It is simple to explain, simple to enforce, and simple to adjust when needed. Do not overcomplicate it unless you have a very specific reason to.

## Context Over Rules

One of the most common questions admins ask is: "Which connectors should I always block?"

The honest answer is: it depends 🤓

There is no universal "always block" list because risk is contextual. A connector that is dangerous in one scenario might be perfectly safe in another. A connector that seems harmless might carry significant risk depending on how it is used.

Take the SharePoint connector as an example. A connector most organizations trust, carries different risk depending on usage. Reading from a document library? Low risk. Deleting files programmatically? That requires more thought. Context determines whether a connector is safe, not the connector name itself.

Or consider the SAP connector. In most organizations I have seen, SAP is treated as a single source of truth. Makers can read from it, but they are not allowed to write back. The risk profile of "read SAP data and display it in an app" is very different from "update SAP records via Power Automate." Both use the same connector, but the risk is completely different.

This is why security assessments should not be static documents. They should be living processes. When a connector is requested, evaluate it in context:
- What is the maker trying to do?
- Are they reading or writing?
- What data is involved?
- What happens if this flow breaks or behaves unexpectedly?

And here is the uncomfortable truth: you should not be making these decisions alone. This is where a Center of Enablement (CoEn) becomes critical. The CoEn sees the entire low-code strategy. They understand business context, technical risk, and organizational priorities. A single admin trying to assess every connector in isolation will either become a bottleneck or make inconsistent decisions.

Connector assessments are not a one-time activity. They are an ongoing responsibility. And they require collaboration, not just technical judgment.

## How Many Policies Do You Actually Need?

The guiding principle is simple: **as few as possible, as many as necessary**.

Every additional Data Policy you create adds complexity. It becomes harder to understand which policy applies to which environment. Makers cannot predict what will work where. And when something breaks, troubleshooting becomes a nightmare because you have to trace through multiple overlapping policies to figure out what is actually being enforced.

Start with one policy that applies tenant-wide or to most environments. Define your baseline: what is Business, what is Non-Business, what is Blocked. Apply it everywhere by default.

Only create additional policies when you have a clear, specific reason:
- A production environment needs stricter controls than the Maker Lab
- A specific business unit has different compliance requirements
- An advanced environment needs access to connectors that should not be available elsewhere

But even then, be cautious. If you find yourself managing five, six, seven different policies, you have likely overcomplicated things. Complexity is the enemy of governance. It creates gaps, inconsistencies, and confusion.

When in doubt, simplify.

## Custom Error Messages That Actually Help

Data Policies will block makers. That is their job. But if you block someone without explaining why or what they should do instead, you have just created frustration.

Custom error messages are one of the most underused features in Data Policies. When a maker hits a policy block, the default message is generic and unhelpful: "This connector is blocked by policy XYZ-2024-v3." That tells them nothing about why it was blocked or what to do next.

Microsoft allows you to customize this message, but the functionality is limited. You can add:
- **A support email address** (e.g., powerplatform-support@yourcompany.com)
- **A link to your governance hub** (e.g., your Power Platform community hub or internal documentation)

That is it. You cannot write custom text that explains what happened or why. You cannot provide contextual guidance in the error message itself.

But even with these limitations, custom error messages are still valuable. When a maker hits a block and sees a support email and a governance hub link, they have a clear next step. They know who to contact. They know where to find answers. They are not stuck guessing.

**Here is where your governance hub becomes critical.** When makers click that link, they should land on a page that includes:
- **An example error message with annotations** showing them how to read it (which connector was blocked, which policy blocked it, where to find help)
- **What happened:** "This connector is restricted by our Data Policy."
- **Why it happened:** "We limit external data connections to protect business information and maintain compliance."
- **What to do next:** "If your use case requires this connector, submit a request through [process] and our CoE will evaluate it."

Showing makers how to read an error message is just as important as customizing it. Most makers do not instinctively understand what "Data Policy" means or why a connector would be restricted. A simple screenshot with callouts explaining each part of the message removes that confusion.

I have written about how to set up custom error messages in detail [here](https://www.michaelroth42.com/post/2024-12-04-customize-error-message/), including an example of how to annotate an error message for your governance hub. That approach works.

The error message itself is limited. But when it points makers to a hub that actually explains the system, teaches them how to read the messages, and gives them a clear escalation path, it becomes a real enablement tool.

Use the custom error message feature. Point it to your hub. And make sure that hub does not just list rules, make sure it teaches makers how to navigate the system.

## The Two Big Mistakes: Security Drift and Silent Policies

If I had to identify the two most common ways Data Policies fail, it would be these:

### Mistake 1: Security Drift

It starts innocently. Someone needs access to a connector "just this once" for a specific project. You make an exception. Then another exception. Then another. Six months later, your baseline policy has so many exceptions that it no longer reflects what you originally intended.

This is security drift, and it is one of the quietest ways governance falls apart (and I will dedicate a whole blog about how to detect Security Drifts, and especially, how to avoid them).

Exceptions are sometimes necessary. But they should be rare, documented, and reviewed regularly. If you find yourself making exceptions constantly, the problem is not the requests, the problem is that your baseline does not reflect reality. Adjust the baseline, do not just pile on exceptions.

And if you do make an exception, set a review date. Nothing should be "temporarily allowed" for a year without anyone questioning whether it is still needed.

### Mistake 2: Policies Without Communication

Data Policies only work if people understand them. If makers do not know what a Data Policy is, do not know which connectors are restricted, and do not know what to do when they hit a block, your policies are just invisible walls that create frustration.

This is why your onboarding learning module (the one you require before granting access to the Maker Lab) should include a section on Data Policies:
- What they are
- Why they exist
- How to read an error message
- Where to go for help

Makers should not have to guess. They should not have to figure it out by trial and error. Explain the system upfront, and you will see fewer violations and less frustration.

## Who Decides What Is Allowed?

Here is a question that does not get asked enough: who is actually responsible for deciding which connectors are allowed and which are not?

The default assumption is usually "the admin." But that is not scalable, and it is not wise. A single admin does not have the context to evaluate every connector request across every business unit, every compliance requirement, and every strategic priority.

This is where a **Center of Enablement (CoEn)** becomes critical. The CoEn is not a single person – it is a cross-functional team that includes:
- IT (technical feasibility and risk assessment)
- Business stakeholders (use case validation and priority)
- Compliance (regulatory and legal considerations)
- Finance (licensing and cost implications)

When a maker requests access to a new connector, the CoEn evaluates it together. They ask:
- What is the business value?
- What is the risk?
- Is this something we want to enable broadly, or only in specific scenarios?
- Does this require new licensing or create compliance obligations?

Take the SAP connector example again. In most organizations, SAP is read-only for Power Platform. Why? Because SAP teams do not want citizen developers writing back to their single source of truth. That is a business decision, not a technical one. And it is a decision that should involve SAP stakeholders, not just the Power Platform admin.

If you are making connector decisions in isolation, you are either going to become a bottleneck (because every request waits on you) or you are going to make inconsistent decisions (because you lack the full context). Neither outcome is sustainable.

Build the CoEn. Make connector governance a collaborative process. Your job as the admin is to implement the decisions, not to make all of them alone (also check out [Growing Centers of Enablement Excellence with Simon Owen](https://www.youtube.com/watch?v=7aDKg0-qU9Y)).

## Connector Risk Is Multidimensional

When you assess a connector, do not just ask "is this risky?" Ask:
- **What is the maker trying to do?** (Read? Write? Trigger external actions?)
- **What data is involved?** (Customer data? Internal only? Public information?)
- **What happens if this fails?** (Minor inconvenience? Compliance violation? Financial loss?)
- **Is this temporary or permanent?** (Experiment? Production workflow?)

The same connector can be low-risk in one scenario and high-risk in another. Reading data from an external API is very different from writing data to it. Sending a notification email is very different from programmatically managing mailboxes.

This is why you cannot rely on a static "approved connectors" list. Risk is not binary. It is contextual, and it changes based on how the connector is used.

Good Power Platform administrators understand this. They do not just say yes or no to connectors, they ask better questions first.

## The Minimum Baseline Checklist

If you want a Data Policy strategy that is sustainable, understandable, and enforceable, here is the minimum:

- [ ] **One baseline Data Policy that applies to most or all environments.** Start simple. Only create additional policies when absolutely necessary.

- [ ] **Clear categorization of connectors into Business, Non-Business, and Blocked.** Avoid the temptation to block everything "just in case." Block what is genuinely risky. Allow what is reasonable. Put the rest in Non-Business.

- [ ] **Custom error messages that include a support contact and a link to your governance hub.** Makers should know what to do when they hit a policy block.

- [ ] **A documented process for connector assessments.** When someone requests a new connector, who evaluates it? What criteria do they use? How long does it take?

- [ ] **A Center of Enablement or similar cross-functional team that makes connector decisions collaboratively.** You should not be making these calls alone.

- [ ] **Regular reviews of exceptions and drift.** If you made an exception six months ago, is it still needed? If your baseline has changed significantly, does it still reflect your strategy?

If you can check all of these boxes, you have a baseline that works. It is not perfect – no policy ever is – but it is clear, enforceable, and understandable.

## A Note on Advanced Connector Policies

Microsoft is evolving connector governance beyond traditional Data Policies. **Advanced Connector Policies (ACP)**, currently in public preview, offer a more granular approach through Environment Groups and an allowlist model. You can control individual actions on connectors (e.g., allow "read" but block "delete" on SQL Server), and you can manage connectors that were previously non-blockable.

If you are interested in the future of connector governance, Advanced Connector Policies are worth exploring. But they require Managed Environments, they are still in preview, and they add significant complexity.

For most organizations starting their governance journey, the Data Policies we have discussed here are the right foundation. Get the basics right first. Then, if your needs outgrow them, consider ACP as the next step.

## Closing Thoughts

A minimum security baseline is not about blocking as much as possible. It is about creating a system that is predictable, understandable, and sustainable.

Makers should know what is allowed. Admins should know why policies exist. And when something is blocked, everyone should know what to do next.

Security drift happens when exceptions pile up without review. Frustration happens when policies exist without communication. Both are preventable if you treat governance as a collaborative, ongoing process rather than a one-time configuration exercise.

In Part 4, we will talk about ownership: how to make it visible, how to prevent orphaned solutions, and why responsibility matters more than control. Because even the best security baseline cannot protect you from solutions that nobody owns.

But before we get there, take a moment to review your own Data Policies. Are they simple enough that makers can understand them? Are they documented well enough that exceptions are rare? Are they collaborative enough that you are not making every decision alone?

If the answer to any of those questions is no, that is where you start. 

And in the end, governance without clarity is not governance. It's just noise 🤷‍♂️

---

I hope you liked this blog. Feel free to find me on [LinkedIn](https://www.linkedin.com/in/michaelroth42/) if you have questions, want to work with me, or just want a nice chat 😎

