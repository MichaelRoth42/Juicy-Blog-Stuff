---
title: Create One Safe Place to Build
description: Learn how to design a Power Platform Maker Environment that balances enablement with governance. DLP alignment, access controls, and when to split environments.
date: '2026-03-16T07:11:06.185Z'
images: 
- images/blog/title-safe-place-to-build.png
author: "Michael Roth"
tags:
  - PowerPlatform
  - Administration
  - Governance
  - PowerApps
  - Microsoft
type: regular
draft: false
---

## Restriction Without Alternative Is Not Governance

In Part 1, we talked about the Default Environment and why it needs clear boundaries. You decided what it's for, you locked down sharing, you disabled viral licenses, and you set expectations. That's good governance.

But if you stop there, you have created a problem.

Because now makers have nowhere to go. They still have problems to solve. They still want to learn. They still need to experiment. And if you have restricted the Default Environment without offering an alternative, you have not created governance, you've created frustration.

![Congratulations](/images/congratulations.png)

Frustrated makers do not stop building. They find workarounds. They use personal accounts. They ask for exceptions. They complain that IT is blocking innovation. And they are not wrong to be frustrated, because you gave them a rule without giving them a path forward.

This is why every restriction must come with a clear alternative. When you limit what is allowed in the Default Environment, you must also define where makers can safely build, experiment, and learn without fear of doing something wrong.

That alternative is the Maker Environment. And getting it right is just as important as locking down the Default Environment.

## What a Maker Environment Actually Is

A Maker Environment is not "the place where governance does not apply." It is not a free-for-all where anything goes. And it is definitely not where you dump everyone who complains about restrictions😁.

A Maker Environment is a **professional playground**. A space where people can experiment, learn, and build early ideas without the pressure of production expectations, but still within the boundaries of your governance principles.

The difference between the Default Environment and a Maker Environment is not the amount of governance. It is the **type** of governance.

In the Default Environment, you optimize for predictability and minimize accidental risk. You assume that anything built there could become important without warning, so you set strict boundaries.

In a Maker Environment, you optimize for learning and enablement. You assume that most things built there will stay experiments, and the few that become important will be identified and migrated. The boundaries are still there, but they are designed to encourage exploration rather than prevent accidents.

This is a crucial distinction. Makers should not feel like they are breaking rules when they use a Maker Environment. They should feel like they are in a space that was designed for them.

## The Core Principles of a Good Maker Lab

Building a Maker Environment is not just about creating a new environment and giving people access. It is about designing a space that balances enablement with sustainability. Here are the principles that make a Maker Lab work:

### 1. DLP Alignment With Production

One of the most common mistakes admins make is creating a Maker Environment where the DLP policy is dramatically different from production. Makers build something using HTTP connectors, premium features, or custom APIs, only to discover later that none of it will work in production because those connectors are blocked.

That is not enablement. That is setting people up for disappointment.

Your Maker Environment DLP should reflect the reality of what you allow in production, just slightly more open (if at all). If custom connectors are never allowed in production, do not allow them in the general Maker Lab either. If HTTP calls require approval and review, make that clear from the start.

The goal is not to block creativity. The goal is to guide makers toward solutions that can actually be deployed. When the DLP in your Maker Lab aligns with production, makers learn the real constraints early and design around them. That saves everyone time and frustration later.

If you want to allow advanced experimentation with connectors that are not allowed elsewhere, create a **separate Advanced Maker Lab** with stricter access controls. But do not mix experimentation with unrealistic capabilities into the general Maker Environment. It creates confusion.

### 2. Access Through Competence, Not Job Title

Not everyone in your organization should have automatic access to the Maker Environment just because they exist in the directory. Giving everyone access without context creates noise, increases support load, and makes the environment harder to manage.

Access to the Maker Lab should be earned, not automatic. That does not mean it should be hard to get, just intentional.

One effective approach is to require a basic learning module before granting access. A 30-minute course that explains:
- What the Power Platform is and what it is not
- What a connector is and why some are restricted
- What Dataverse is and when to use it
- What the Maker Lab is for and what happens when something becomes important

Once someone completes the module, they are added to a Security Group that grants access to the Maker Environment. This small friction accomplishes several things:
- It filters out people who are just curious but not committed
- It ensures that everyone entering the space has a baseline understanding
- It gives you a scalable onboarding pipeline

This is not gatekeeping. This is setting people up for success. Makers who understand the platform are less likely to build things that violate policies, less likely to need constant support, and more likely to build solutions that can actually be deployed.

### 3. Start Simple, Split When Necessary

Do not create ten environments on day one just because you think you might need them later. Start with one general Maker Lab for the majority of your makers, and split only when monitoring shows that you need to.

A single Maker Lab works well for:
- Canvas apps
- Standard Power Automate flows
- Early Dataverse experiments with custom tables
- Learning and skill development

But some scenarios require separation:

**Custom Connector Lab:** When makers need to experiment with HTTP calls, external APIs, or custom connectors that are too risky for the general population, create a separate environment with stricter access controls. Once those connectors are reviewed and approved, you can choose to make them available in the general Maker Lab.

**Department Labs:** If monitoring shows that a specific business unit or department has consistent, high-volume maker activity, consider giving them their own environment. This reduces noise for everyone else and gives that team more autonomy. But do not do this preemptively – only when the data justifies it.

The principle is simple: **start with one, split when complexity or volume demands it**. Every additional environment adds management overhead. Only create them when the benefit outweighs the cost.

### 4. Dataverse Is the Separation Trigger

Dataverse is where things get complicated, because multiple makers working on the same Dataverse instance can create conflicts that do not exist with Canvas apps or flows.

If makers are just learning how Model Driven Apps work and experimenting with standard tables like Account or Contact, that is fine in a shared Maker Lab. The data is test data, nobody expects production quality, and conflicts are learning opportunities.

But the moment makers start using Dataverse standard tables for real business processes, or when they begin building solutions that rely heavily on custom tables and relationships, they need their own environment. Because now:
- Field ownership becomes unclear
- Data can be accidentally mixed or deleted
- One maker's changes can break another maker's app

**Use Dataverse as a trigger.** When monitoring shows that someone is building a serious Model Driven App or relying on Dataverse for a real workflow, that is the signal to create a separate environment for them or their team.

This is basically the recognition that their work has matured beyond the experiment phase 🏆

### 5. Communicate Lifecycle Expectations Early

The Maker Lab is explicitly not a production environment. That needs to be clear from the moment someone gets access.

What this means in practice:
- Apps and flows in the Maker Lab can be deleted if they violate policies or are abandoned
- There are no SLA guarantees
- Ownership stays with the maker. If they leave, their solutions may not be maintained
- If something becomes business critical, it must be migrated to a production environment

This is not a threat, merely clarity. When makers understand that the Maker Lab is a temporary space for learning and early development, they are less likely to treat it as production. And when something does become important, they know the next step is to request a production environment and plan a proper migration.

Set these expectations in the onboarding material, include them in your governance hub, and repeat them when violations occur. Lifecycle thinking prevents most of the governance problems that happen later.

## One Lab or Many? When to Split

The default answer should always be: **one general Maker Lab for most people**.

This works because:
- It is simple to explain
- It reduces administrative overhead
- It creates a shared community of makers who can learn from each other
- Monitoring is centralized

You only split when one of these conditions is true:

**Condition 1: Advanced Use Cases**  
Makers need connectors or capabilities that are too risky for general access (HTTP, custom connectors, external APIs). Create a separate **Advanced Maker Lab** with limited access and stricter review processes.

**Condition 2: High-Volume Business Units**  
A department or team consistently produces a large volume of apps and flows, and shared resources are creating friction. Create a **Department Lab** for that team, but only after monitoring proves the need.

**Condition 3: Serious Dataverse Usage**  
Makers are building Model Driven Apps with real business logic, or using standard tables for actual workflows. Create a **dedicated environment** for that project or team.

Do not split preemptively. Do not create environments "just in case." Every environment you create adds complexity. Only split when monitoring and usage patterns justify it.

## The Minimum Maker Environment Baseline

If you want a Maker Environment that actually enables people without creating chaos, here is the minimum baseline:

- [ ] **DLP policy aligned with production.** Makers should not be able to build things in the Maker Lab that will never work in production. The policy should be slightly more permissive than production, but not dramatically different.

- [ ] **Access through a Security Group, ideally gated by a learning module.** Not everyone gets automatic access. Require basic platform knowledge before granting entry.

- [ ] **Clear communication about what the Maker Lab is for.** Document this in your governance hub, link to it from the environment description, and repeat it in onboarding. Makers should understand that this is a safe space for learning and early development, not a production platform.

- [ ] **Lifecycle expectations defined.** Apps and flows here are not permanent. If something becomes important, it must be migrated. If something is abandoned, it may be cleaned up.

- [ ] **A migration path to production.** Makers need to know how to request a production environment when their solution matures. This should be documented and easy to find.

- [ ] **Monitoring in place.** You cannot manage what you do not measure. Set up monitoring to track what is being built, who is building it, and when solutions are starting to look production-ready.

If you can check all of these boxes, your Maker Environment is no longer a dumping ground. It becomes a real enablement tool.

## This Is Enablement, Not Permission

The Maker Environment is not where you send people to get them out of your way. It is not a compromise between "let people build" and "keep things under control."

It is an intentional space where makers can learn, experiment, and build early solutions within clear boundaries. It is where innovation happens safely. And it is where you discover which makers have the skills and commitment to build things that matter.

When you design a Maker Environment with clear principles - DLP alignment, intentional access, lifecycle expectations, and monitoring – you create a system that scales. Makers know where they can build. Admins know what to expect. And the organization benefits from solutions that were tested and refined before they ever reached production.

## Essential Environment Settings for Your Maker Lab

Creating a Maker Environment is not just about clicking "New Environment" in the admin center. The settings you configure determine whether the environment becomes a real enablement tool or just another unmanaged space that creates problems later.

Here are the essential settings that every Maker Lab should have:

### 1. Security Group Assignment

Do not leave the Maker Lab open to "Everyone" in your tenant. Assign it to a dedicated Security Group that controls who has access.

This gives you several advantages:
- **Controlled onboarding:** You can require makers to complete a learning module before being added to the group
- **Scalable access management:** Adding or removing people becomes a simple group membership change
- **Visibility:** You know exactly who has access and can track it over time

The Security Group should be named clearly (e.g., "Power Platform Makers" or "Maker Lab Access") and managed by your governance team or IT. Do not let it become a self-service free-for-all.

### 2. Enable Dataverse Audit (With Short Retention)

Dataverse Audit is one of those features that many admins avoid in non-production environments because they assume it is unnecessary overhead. That assumption creates a problem: makers learn to build without audit, and then they are surprised when production environments require it.

Activate Dataverse Audit in your Maker Lab, but set the retention period to 30 days instead of the default (which is 'forever'🤷‍♂️). This gives you enough visibility to understand what happened when something breaks, while keeping capacity consumption manageable.

**What Dataverse Audit does:**
- Tracks create, update, and delete operations on Dataverse records
- Records who made the change, when it happened, and what the old and new values were
- Allows you to investigate issues after the fact (e.g., "Who deleted this record?")
- Provides a compliance trail when needed

**What Dataverse Audit does NOT do:**
- It does not prevent mistakes. Audit is retrospective, not preventive. If someone deletes a record, audit tells you who and when, but it does not stop the deletion from happening.
- It does not automatically restore data. You see what was deleted, but recovery requires manual intervention or a backup.
- It does not track everything. Audit only tracks changes to data, not configuration changes like security role modifications or environment settings.
- It does not replace proper backup strategies. Audit is forensic evidence, not a recovery mechanism.

Enabling audit in the Maker Lab teaches makers that their actions are visible and traceable. This is not surveillance. This is accountability. When makers understand early that changes leave a trail, they are more thoughtful about what they build and how they test it.

Set the retention to 30 days to balance visibility with capacity costs. For most Maker Lab scenarios, 30 days is enough to investigate recent issues without filling up your Dataverse storage with logs from abandoned experiments.

**[Screenshot placeholder: Power Platform Admin Center → Select Environment → Environment Settings → Audit Settings → Start auditing, set retention to 30 days]**

### 3. Create Flows and Apps in Solutions by Default

One of the most underused settings in Power Platform is the ability to automatically create new canvas apps and cloud flows inside solutions instead of leaving them as standalone objects. This setting is transformative for governance, but only if makers understand why it exists.

Enable this setting in your Maker Lab. Do not wait until makers are "ready" for solutions. Make solutions the default from day one.

**Why this matters:**

Solutions are how you package, version, and move Power Platform components between environments. If makers build apps and flows outside of solutions, migrating them to production later requires manually exporting, packaging, and cleaning up dependencies. It is tedious, error-prone, and frustrating (and a typical project for IT consultants who do this kind of thing all the time. So save yourself the expense and train your makers early on 😉).

When you enable "Create flows and apps in solutions by default," every new app or flow is automatically placed in a solution. Makers still need to create or choose a solution, but once they do, everything stays organized. Migration becomes straightforward. Versioning becomes possible. ALM becomes real.

**What makers need to understand:**

A solution is not bureaucratic overhead. It is a container that makes their work portable and manageable. If they build something useful in the Maker Lab and want to move it to production, the solution is what makes that possible.

This is why your onboarding learning module should include a basic explanation of solutions:
- What they are (containers for components)
- Why they exist (migration, versioning, structure)
- How to create one (simple, takes 30 seconds)

Once makers understand that solutions are not extra work but future-proofing, the setting stops feeling like a restriction and starts feeling like good practice.

**What this setting does:**
- Forces makers to specify a solution when creating a new app or flow
- Keeps all components organized and migration-ready
- Encourages structured thinking about what belongs together
- Prepares makers for production workflows

**What this setting does NOT do:**
- It does not automatically create solutions for makers. They still need to create or select one.
- It does not enforce naming conventions or solution structure. You can still have messy solutions if makers do not organize their work.
- It does not replace proper ALM pipelines. Solutions are the foundation, but deployment still requires a process.

Enable this setting in the Maker Lab, and make sure your onboarding material explains why. Makers should not learn one way of working here and then be forced to unlearn it when they move to production. **Teach them the right habits from the start.**

**[Screenshot placeholder: Power Platform Admin Center → Environment Settings → Features → Canvas apps and Flows in Solutions = On]**

### 4. Set Up Capacity Monitoring

Maker Labs can fill up quickly with test data, experimental Dataverse databases, and audit logs. If you do not monitor capacity, you will eventually be surprised when storage runs out and makers can no longer create new databases or apps.

This is especially important if you enabled Dataverse audit and multiple makers are actively building. Audit logs consume storage, and while 30-day retention helps, the volume can still add up in an active environment.

Set up capacity alerts so you are notified before the environment reaches critical storage levels. This gives you time to clean up abandoned solutions, remove test data, or allocate additional capacity if needed.

Regular cleanup should be part of your maintenance routine. If a solution has not been touched in 90 days and the owner confirms it is no longer needed, remove it. If test data is piling up in Dataverse tables, schedule periodic purges. The Maker Lab should feel active and maintained, not like a digital junkyard.

Microsoft provides detailed guidance on monitoring capacity and setting up alerts in the [Power Platform Admin Center documentation](https://learn.microsoft.com/en-us/power-platform/admin/capacity-storage). Use it.

---

These four settings turn a generic environment into a real Maker Lab. They enforce good habits, prepare makers for production realities, and keep the environment manageable. None of them are optional if you want a Maker Environment that actually scales.

## Communicate Governance Actively, Not Passively

Environment settings enforce behavior, but they do not create understanding. Makers need to know why these settings exist and what is expected of them. Do not rely on passive discovery mechanisms like documentation that makers need to search for. Governance communication should be active and unavoidable.

When someone gets access to the Maker Lab:
- **Send a welcome email** with the purpose, the rules, and a link to your governance hub
- **Require an onboarding learning module** that explains what the Maker Lab is for, what solutions are, and what happens when something matures
- **Pin governance guidance** in your Maker community channel (Teams or Slack)
- **Reference the governance hub** in your DLP custom error messages so makers know where to find answers when they hit a policy block

Makers should encounter governance naturally as part of their workflow, not as something they need to actively seek out. The settings above enforce good behavior, but communication is what creates understanding and buy-in.

Without active communication, even the best environment settings will feel like arbitrary restrictions. With it, governance becomes a shared understanding rather than a set of invisible rules.

In Part 3, we will talk about the minimum security baseline that applies everywhere, not just in the Maker Lab, but across your entire platform. Because governance is not about perfect security. It is about predictable, understandable rules that people can actually follow.

But before we get there, take a moment to think about your own Maker Environment. Does it exist? If it does, does it follow these principles? If it does not exist yet, this is your starting point.

And in the end, governance without alternatives is not governance. It's just friction 🤷‍♂️

---

I hope you liked this blog. Feel free to find me on [LinkedIn](https://www.linkedin.com/in/michaelroth42/) if you have questions, want to work with me, or just want a nice chat 😎

