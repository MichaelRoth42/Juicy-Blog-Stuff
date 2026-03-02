---
title: Make Ownership Visible
description: Ownership prevents chaos. Learn how to track who owns what, prevent orphaned solutions, and build a system that scales with impact, not with existence.
date: '2026-03-09T07:00:00.000Z'
images: 
- images/blog/title-part4-ownership.png
author: "Michael Roth"
tags:
  - PowerPlatform
  - Administration
  - Governance
  - Lifecycle
  - Microsoft
  - GovSeries
type: regular
draft: true
---

## Why Ownership Matters More Than You Think

You can have perfect Data Policies. You can have a well-designed Maker Lab. You can have clear environment boundaries. But if nobody knows who owns what, your governance will still fall apart.

Ownership is the foundation that everything else builds on. It determines who gets called when something breaks. It determines who decides whether a solution still matters. It determines whether an app gets maintained or abandoned.

Without visible ownership, you end up with orphaned solutions that nobody dares to touch. Apps that run in production but have no documented owner. Flows that stop working and nobody knows who built them or why. And when you try to clean up, you discover that deleting anything feels risky because you cannot be sure it is not critical to someone, somewhere.

This is not a technical problem. It is a visibility problem. And visibility problems are solvable.

## Business Owner vs. Technical Owner

Not every solution needs the same level of ownership documentation. A personal helper app that one maker uses for themselves does not need a formal ownership record. But once a solution is used by multiple people, supports a business process, or runs in production, ownership becomes critical.

For production solutions, you need two types of owners:

**Technical Owner:** The person who built it, maintains it, and understands how it works. This is usually the maker, but it could also be someone from IT if the solution was handed off. The Technical Owner is responsible for keeping the solution running, fixing issues, and making updates when needed.

**Business Owner:** The person who is accountable for the business process or outcome that the solution supports. This might be a department manager, a team lead, or a process owner. The Business Owner decides whether the solution is still needed, prioritizes feature requests, and escalates when something is not working.

Not every solution will have both. Smaller solutions might only have a Technical Owner. That is fine. The critical part is that someone is clearly responsible. Quite often, especially for smaler solutions, one person can have both roles at once: technical- and business owner, and this is absolutely fine.

But for business-critical solutions—anything that runs daily, supports important workflows, or affects multiple users—you need both roles and two different persons. Because when the Technical Owner leaves the company or goes on parental leave, the Business Owner can escalate and ensure continuity. And when the Business Owner changes priorities, the Technical Owner knows who to talk to.

## The Two-Owner Rule for Critical Solutions

Here is a simple rule that prevents most ownership problems: **every business-critical app or flow must have two owners**.

It does not matter whether those are two Technical Owners, a Technical Owner and a Business Owner, or a primary and a backup contact. What matters is that there are two people who know the solution exists, understand what it does, and can respond when something goes wrong.

Why two? Because one is fragile. People get sick. People go on vacation. People leave companies. People switch roles. If only one person knows how a critical solution works, you are one life event away from an unsupported app that nobody dares to touch.

Two owners create redundancy. Not expensive, complicated redundancy—just the basic acknowledgment that critical things should not depend on a single person.

This does not mean you need two owners for every personal productivity app in your Maker Lab. Governance should scale with impact, not with existence. A flow that sends you a daily reminder does not need a backup owner. A flow that processes invoices for the entire finance department does.

And if you wonder "hmmm, I would like to know, who can make this decision in the end? Who decides about how critical or important a flow or an app is?!", then you're at the right place 🤓:

## This Is Not Just an Admin Decision

Here is something that often gets overlooked: deciding what level of ownership is required for different types of solutions is not a purely technical decision. It is a business decision.
As the admin, you can implement ownership tracking. You can build the automation. You can enforce the policies. But you should not be deciding alone what constitutes "business-critical" or when a solution requires two owners instead of one.
This is where leadership needs to be involved. Not to micromanage every app, but to define the principles:

- What makes a solution critical enough to require formal ownership?
- What are the consequences if a critical solution loses its owner?
- How much risk is the organization willing to accept with single-owner solutions?
- What level of documentation is required before a solution can be promoted to production?

These questions determine how much overhead your ownership processes will create. If leadership says "every app needs two owners and full documentation," you will have a very different system than if they say "only business-critical apps need formal ownership."
The Power Platform is not a self-managing system. It requires conscious decisions about risk, responsibility, and resource allocation. And those decisions cannot be made by IT alone.

Your job as the admin is to present the options, explain the trade-offs, and implement whatever strategy leadership agrees to. But if you try to make these calls yourself, you will either become a bottleneck (because every ownership question waits on you) or you will make inconsistent decisions (because you lack the full business context).

This is the same principle we discussed in [INSERT LINK: Part 0: governance starts with clarity], and clarity requires leadership involvement. Ownership policies are no exception.

Use judgment. But when in doubt, add a second owner. It is easier to do it upfront than to scramble later when the primary owner is unreachable.

## Where to Track Ownership

Ownership only works if it is visible. If ownership information lives in someone's head, in scattered emails, or in a Word document that nobody can find, it might as well not exist.

You need a central place where ownership is documented and kept up to date. The good news is that you do not need a fancy system. You need something that works.

**The best option: Center of Excellence (CoE) Starter Kit.**

The CoE Starter Kit automatically tracks apps, flows, and their creators. It pulls this information from your tenant and stores it in Dataverse. It is built by Microsoft, maintained actively, and free to use. If you can deploy it, use it. It will save you an enormous amount of manual tracking work.

**If CoE Starter Kit is not an option:**

Some admins do not have the permissions or infrastructure to deploy the CoE Starter Kit. Maybe they work for a subsidiary with limited admin rights. Maybe their organization does not allow Power Platform solutions to run with elevated permissions. That is fine.

In that case, use whatever works for you:
- A Dataverse table where makers or admins log ownership manually
- A SharePoint list that gets updated when solutions are promoted to production
- A simple tracking flow that pulls app and flow metadata and writes it to a list

It does not need to be sophisticated. It needs to be accessible, searchable, and maintained. A SharePoint list that people actually use beats a fancy tracking system that nobody updates.

## IT Production Environment and the Handoff Process

As solutions mature and become business-critical, they often outgrow the Maker Lab or departmental environments. When something becomes truly important—used daily, relied on by many people, or core to a critical business process—it should be hosted in a production environment managed by IT.

This is not a punishment, but rather recognition that the solution has graduated from experimentation to infrastructure. And infrastructure requires different governance.

In an **IT Production environment**, solutions are treated with the same rigor as other IT-managed systems. They get proper documentation, formal ownership records, and support commitments. But to get there, the solution needs to go through a handoff process.

**The handoff process should include:**

- **Evaluation of the solution:** Does it meet technical standards? Is it built in a way that can be maintained long-term?
- **Documentation:** What does the solution do? Who uses it? What are the dependencies? What happens if it breaks?
- **Ownership transfer or confirmation:** Who will be the Technical Owner going forward? Who is the Business Owner?
- **Support agreement:** What are the SLAs? Who handles incidents? How are changes requested?

This is not bureaucracy for its own sake, it is the minimum information needed to support something properly. If IT is expected to keep a solution running, they need to understand what it does and who depends on it.

The handoff process does not need to be long or complicated. A one-page template with the basics is enough. But it must exist. Otherwise, you end up with production solutions that IT inherited without context, and that creates risk.

## Automated Ownership Tracking and Escalation

Tracking ownership manually is not sustainable at scale. If you have dozens or hundreds of apps and flows, you need automation to keep ownership records accurate.

The Center of Excellence Starter Kit handles much of this automatically. It scans your tenant, identifies apps and flows, logs their creators, and tracks changes. If you are not using CoE, you can build similar functionality with Power Automate flows that query the Power Platform Admin connectors and write results to a tracking list.

But automation is not just about logging ownership. It is also about detecting when ownership becomes a problem.

**Here are the scenarios you should monitor for:**

### 1. Ownerless Solutions

When a maker leaves the company, their apps and flows do not disappear—but what happens next depends on how they were built. If the flow uses connections tied to the owner's account (common for scheduled and automated flows), it will start failing once that account is disabled. In some cases, flows are automatically disabled when the owner account becomes invalid. Either way, you end up with a solution that nobody can fix, update, or safely maintain. This is a ticking time bomb.

You should have a process that detects ownerless solutions and escalates them:
- Flag any app or flow where the creator's account is disabled or no longer exists
- Notify the Business Owner (if one exists) that the Technical Owner has left
- If no Business Owner exists, notify IT or the environment admin
- Evaluate whether the solution is still needed
- If yes, assign a new Technical Owner
- If no, archive it

Do not let ownerless solutions sit indefinitely. The longer they run without an owner, the harder it becomes to figure out what they do and whether they matter.

### 2. Single-Owner Critical Solutions

Even if the owner is still active, a business-critical solution with only one owner is risky. Your automation should flag any solution marked as critical that does not have a backup or co-owner.

This does not need to be aggressive. A simple notification to the owner and their manager asking them to assign a co-owner is enough. Most people will comply if you explain why it matters.

### 3. Capacity-Driven Escalation

If an environment is running low on capacity, you need to identify which solutions are still actively used and which can be removed. This is where ownership becomes critical.

Send a notification to the owners of apps and flows in that environment:
- "This environment is nearing capacity limits. Please confirm whether this solution is still needed."
- If the owner does not respond within a reasonable timeframe (e.g., 14 days), escalate to the co-owner or Business Owner
- If still no response, evaluate based on usage data (see next section)

Capacity pressure is a forcing function. It makes ownership matter because ignoring it has real consequences.

### 4. Usage-Based Evaluation

**"Last Used" is the gold standard for tracking app relevance.** It tells you whether people are actually using the solution, not just whether someone modified it recently.

The Center of Excellence Starter Kit can track "Last Used" via Office 365 Audit Logs. It shows when an app was last launched and by how many unique users. This is incredibly valuable for identifying abandoned solutions.

But there is a catch: tracking "Last Used" requires access to audit logs, which means you need either:
- The CoE Starter Kit with proper permissions
- Purview (which requires E5 licensing)
- A custom solution using the Office 365 Management API

If you do not have audit access (common for admins without Purview or elevated permissions) you have to fall back on **"Last Modified Date"** as a proxy. It is not perfect (an app can be used daily without being modified), but combined with "number of users shared with" and periodic check-ins with owners, it gives you enough signal to identify truly abandoned solutions.

Do not let the lack of perfect telemetry stop you from acting. Approximate data is better than no data.

![Approximate data](/images/approximate-knowledge.png)

## Onboarding New Owners

When a solution changes hands, whether due to someone leaving, a role change, or a deliberate handoff, the new owner needs context. Throwing someone into ownership without preparation is a recipe for failure.

Create a simple onboarding checklist for new co-owners or replacement owners:

- **Where is the documentation?** (README, inline comments, external docs)
- **Who are the primary users?** (Who relies on this solution?)
- **What are the critical dependencies?** (External APIs, data sources, scheduled triggers)
- **What happens if it breaks?** (What is the business impact?)
- **Who do I contact for help?** (Previous owner, IT support, Business Owner)

This does not need to be a 20-page document. A one-page summary is enough. The goal is to give the new owner enough context to avoid feeling completely lost.

And here is the key: this checklist should be filled out **when the solution is promoted to production**, not when someone leaves. If you wait until the original owner is gone, the knowledge is already lost.

## What to Do With Ownerless Solutions

When you identify a solution that has no active owner, do not immediately delete it. Deleting something without understanding its impact is risky. Instead, follow a clear evaluation process:

**Step 1: Check usage data.**

If the solution has not been used in 90+ days and was shared with only one or two people, it is probably safe to archive. If it is used daily by dozens of people, it is clearly still important.

**Step 2: Attempt to contact the Business Owner.**

If the Technical Owner is gone but there is a documented Business Owner, reach out. Ask whether the solution is still needed and whether they can identify a new Technical Owner.

**Step 3: If no Business Owner exists, use environment context.**

If the solution is in a departmental environment, contact the department's admin or manager. If it is in an IT Production environment, escalate to IT.

**Step 4: Archive, do not delete.**

If the solution appears abandoned and nobody claims ownership within a reasonable timeframe (e.g., 30 days), export it as a solution package and archive it. Store the export in a secure location with metadata about when it was archived and why.

Do not just delete it. Archiving gives you a recovery path if someone later realizes they still needed it.

**Step 5: Remove from production only after archiving.**

Once archived, you can safely remove the solution from the environment to free up capacity. But always archive first.

## Documentation: Keep It Minimal, Make It Useful

Good documentation makes ownership transitions possible. And everyone loves to read good documentation. Period. The problem is, nobody wants to write good documentation.

>And bad documentation is worse than no documentation because it creates false confidence.

Here is the problem: most people are terrible at writing documentation, and most documentation templates are too long. If you ask makers to fill out a 10-page form, they will either skip it or fill it with useless generic text just to get past the requirement.

Instead, use a **one-page template** that focuses on the essentials:

### Minimal Documentation Template

**Solution Name:**  
**Owner(s):**  
**Business Purpose:** (One or two sentences: What does this solve? Why does it exist?)  
**Primary Users:** (Who relies on this? A team? A department? Specific people?)  
**Key Dependencies:** (External APIs, data sources, scheduled jobs, other apps/flows)  
**What happens if it breaks?:** (Business impact: Minor inconvenience? Workflow stops? Compliance risk?)  
**Where to find help:** (Who to contact? Where are additional notes or comments?)

That is it. Six questions. Most of them can be answered in a single sentence. This is not a technical design document. It is a triage guide for the next person who has to figure out what this solution does.

If you want more detailed technical documentation (architecture diagrams, data flow maps, API specs), that is great. But do not make it a requirement for every solution. Require the minimum. Encourage the extra.

## When Lifecycle Status Helps (And When It Doesn't)

Some organizations track lifecycle status for their solutions: Development, Production, Deprecated, Archived. This can be helpful, especially at scale, but it is not always necessary.

**Lifecycle status is useful if:**
- You have hundreds of solutions and need a way to filter what matters
- You have formal ALM pipelines and want to track promotion stages
- You need to distinguish between active production and deprecated solutions that are still running but should not be enhanced

**Lifecycle status is overkill if:**
- You have fewer than 50 solutions and can track them informally
- Your governance is still early-stage and adding complexity will slow adoption
- Environment separation already makes the distinction clear (Maker Lab = dev, IT Prod = production)

If you decide to use lifecycle status, keep it simple. Three or four stages are enough. Do not create ten different states that nobody can remember.

And critically: lifecycle status is not a replacement for ownership. A solution can be marked "Production" and still have no documented owner. Status is metadata. Ownership is responsibility.

## The Ownership Baseline Checklist

If you want ownership that actually works, here is the minimum:

- [ ] **Every business-critical solution has two owners.** This prevents single points of failure.

- [ ] **Ownership is tracked in a central, searchable location.** Use CoE Starter Kit if possible, or a Dataverse/SharePoint list if not.

- [ ] **Ownerless solutions are detected and escalated automatically.** A scheduled flow flags apps/flows where the owner's account is disabled or missing.

- [ ] **Single-owner critical solutions are flagged and reviewed regularly.** You cannot mandate two owners everywhere, but you can at least make the risk visible.

- [ ] **New owners get a basic onboarding checklist.** Do not assume they will figure it out on their own.

- [ ] **Usage data informs decisions about abandoned solutions.** "Last Used" if you have audit access, "Last Modified" + user count if you do not.

- [ ] **Ownerless solutions are archived, not deleted.** Always keep a recovery path.

- [ ] **Minimal documentation exists for production solutions.** One-page template. Six questions. No more.

If you can check these boxes, ownership stops being a mystery and starts being a system.

## Closing Thoughts

Ownership is not glamorous. It is not exciting. It does not feel like "real" governance work. But it is the foundation that makes everything else possible.

Without ownership, you cannot safely clean up environments. You cannot evaluate risk. You cannot plan lifecycle transitions. You cannot even answer the basic question: "Who do I call when this breaks?"

Good ownership processes do not require sophisticated tools or complex workflows. They require clarity, consistency, and just enough automation to keep things accurate without creating overhead.

Track what matters. Ignore what does not. Make ownership visible so that when something goes wrong, everyone knows exactly who to talk to.

In Part 5, we will talk about when IT should get involved and how to define the thresholds that trigger a handoff from makers to IT. Because ownership is not just about knowing who built something—it is about knowing when a solution has outgrown the person who created it.

But before we get there, review your own ownership practices. Do you know who owns your most critical solutions? Do those owners have backups? If the answer is no, that is where you start.

And in the end, governance without ownership is not governance. It's just hoping 🤷‍♂️

---

I hope you liked this blog. Feel free to find me on [LinkedIn](https://www.linkedin.com/in/michaelroth42/) if you have questions, want to work with me, or just want a nice chat 😎

