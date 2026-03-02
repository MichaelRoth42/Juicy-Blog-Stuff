---
title: Why Your Governance Strategy Fails – And It's Not the Settings
description: Governance doesn't start in the Admin Center. Before configuring policies, answer four questions no DLP can solve. This is where the Governance Series begins.
date: '2026-02-10T07:11:06.185Z'
images: 
- images/blog/title-why-your-governance-fails.png
author: "Michael Roth"
tags:
  - PowerPlatform
  - Administration
  - Governance
  - Microsoft
type: regular
draft: false
---

# Part 0 – Start With Your Head, Not With Settings

## About This Series

A few years ago, I wrote a governance series that focused heavily on technical settings and configurations. It was useful at the time, but I have learned a lot since then – both from my own work and from conversations with hundreds of Power Platform admins across the world.

This is the updated version. A series for anyone who is new to Power Platform governance, whether you have been an admin for years or this is your first week in the role. We will work through this together, step by step, starting with mindset and moving toward practical implementation.

Between the main parts, I will publish deeper technical articles that go into specific topics in more detail. But the core series is designed to give you a clear foundation: what governance actually is, why it matters, and how to build it in a way that enables people instead of blocking them.

If you have read my old series, this one will feel different. Less checklist, more principles. Less "click here," more "think about this first." That is intentional.

So let's get started 🚀

---

## The Problem Starts Before You Open the Admin Center

Let me tell you a story you've probably lived through.

A maker builds an app in two hours. It's elegant, it solves a real problem, and everyone's happy. Six months later, you discover it in the Default Environment. Three hundred people are using it daily. Nobody knows who owns it. There's no backup. And the maker? They left the company three months ago.

Now the app is critical. Now it's your problem. Now you're the one who has to figure out what happens when it breaks.

So what went wrong? Was it the app? Was it the maker? Was it Microsoft?

No. It was the missing governance mindset before anyone built anything at all.

## The "It's Easy" Illusion

Microsoft tells you that Power Platform is easy. And they're not lying – it genuinely is easy to *start*. You can build a functional app in an afternoon. You can automate a process without writing a single line of code. That's the entire point.

But here's what "easy" doesn't mean: it doesn't mean *simple*. It doesn't mean *risk-free*. And it definitely doesn't mean *no architecture required*.

Low code lowers the barrier to entry. It does not lower the complexity threshold. It just hides it better.

When you build in traditional development, the complexity is visible. You see databases, APIs, deployment pipelines, error handling. You *feel* the architecture because you have to explicitly design it.

Power Platform abstracts all of that away. The database appears when you need it. The API calls happen in the background. Deployment is a button click. That's incredibly powerful – but it creates a dangerous illusion: the illusion that you're not building production systems.

You are. Whether you intended to or not.

The maker optimizes for "problem solved." That's their job, and they're good at it. You, as the admin, optimize for "system sustainable." Both perspectives are legitimate. Both are necessary. But they need to be balanced, and that balance doesn't happen automatically.

> Microsoft optimizes for adoption. You optimize for not getting called at 3 AM because someone's critical app is down and nobody knows how to fix it.

## Governance Starts With Four Questions, Not Four Policies

Most admins I meet start in the same place: the Admin Center. They open it up, look at DLP policies, maybe enable some connectors, block others, and call it governance.

That's not governance. That's configuration.

Governance starts in your head. It starts with four questions that have nothing to do with settings:

![How many questions do you see?](/images/FourQuestions.jpg)

**1. What do we want to enable?**

Not "what do we want to prevent" – that comes later. Start with enablement. What problems should people in your organization be able to solve? What capabilities do you want makers to have access to? What does "empowered workforce" actually mean in your context?

If you can't answer this clearly, your governance will always feel restrictive, because you'll be optimizing for risk instead of value.

**2. What do we want to protect?**

Data? Systems? Reputation? Customer trust? Compliance requirements? All of the above?

You can't protect everything equally, so you need to know what matters most. Without this clarity, you'll end up with DLP policies that make no sense – strict in random places, loose in others, and nobody understands why.

**3. Where do we accept risk?**

This is the question most admins avoid, but it's the most important one. You cannot eliminate all risk. Low code exists *because* businesses decided that the risk of slow IT delivery was worse than the risk of citizen development.

So where do you consciously accept risk? In a maker environment? In self-service scenarios? For specific business units? Make it a decision, not an accident.

**4. Where don't we accept risk?**

Here's where you draw hard lines. Production systems? Customer-facing apps? Regulated data? Areas where a mistake could cost you legally or financially?

Define this clearly, and suddenly your governance has structure. Everything else follows from these answers.

> Settings are just the technical implementation of these decisions. If you can't answer these four questions, your DLP policies are just noise.

But now, read carefully, here comes the important part:

### If You Can't Answer These Questions, You're Not Ready....And You Shouldn't Be Alone

This is where most admins get stuck. Not because they lack technical skill, but because these are not technical questions. They are business questions. Strategic questions. Questions that define risk appetite, compliance boundaries, and organizational priorities.

Here's the uncomfortable truth: Power Platform capabilities exist in your tenant whether leadership knows about them or not. Tenant isolation is disabled by default. Custom connectors work in the Default Environment. Self-service purchases are enabled. Viral licensing spreads silently. All of this happens without a single conscious decision from anyone in your C-suite.

This is not a gap you can close alone. If leadership has not explicitly decided whether to enable, tolerate, or restrict Power Platform, then your tenant is running on Microsoft's defaults and those defaults assume you want maximum adoption with minimal friction. That might not be what your organization can safely handle (trust me, it's what very few organization can, and even want to handle 😅).

So before you build policies, before you lock anything down, take those four questions to leadership. Make it clear that not deciding is still a decision. One that leaves the platform wide open. 
**Your** job is to implement **their** strategy. **Their** job is to define what that strategy should be.

If they have never thought about Power Platform governance, you are not behind. You are exactly where you need to be: at the beginning. Start the conversation now.

Before you create your first DLP policy, write down your answers to these four questions. If you can't, you're not ready to configure anything yet. Talk to leadership. Talk to business stakeholders. Get clarity first.

## Defaults Are Dangerous When Left Unreflected

Here's something that applies everywhere in Power Platform, not just in policies: anything that exists as a default will eventually get used.

The Default Environment isn't a technical detail. It's a strategic decision and it's your first one. Everything that exists as a default will eventually get used, whether you planned for it or not. Microsoft's defaults optimize for adoption. Your defaults need to optimize for sustainability.

Microsoft's defaults are not designed for your compliance requirements. They're designed for adoption. Share with everyone? Enabled by default. Self-service purchases? Enabled. Viral licensing? Spreading silently.

That's not a criticism of Microsoft. It's product design. They want people to use the platform, and friction kills adoption. But their defaults are not *your* governance.

Your job is to make defaults visible, then make conscious choices about them. We'll dig deep into this in Part 1, starting with the Default Environment, but the principle applies everywhere: make your defaults conscious choices, not accidents waiting to happen.

## People Are the Core, Not Policies

If there's one thing I want you to take from this article, it's this: governance is a social system, not a technical one.

You can have the most sophisticated DLP policies in the world. You can lock down connectors, enforce naming conventions, require business justifications for every environment. And it will all fail if people don't understand why.

Rules without communication create resistance. Policies without context create confusion. Blocking without offering alternatives creates shadow IT.

The admin is not a gatekeeper. The admin is a translator.

You translate between business ("we need to move fast"), IT ("we need stability"), risk ("we need compliance"), and reality ("we have three admins for five thousand users"). Your job is to find the balance that lets all of these perspectives coexist.

Governance should feel like clarity, not restriction. It should reduce cognitive load, not add to it. When makers understand *why* certain things are blocked, they stop seeing you as the person who says no and start seeing you as the person who helps them build better.

> If governance feels like a fight between IT and the business, you're doing it wrong.

## This Series Is About Decisions, Not Checkboxes

Over the next weeks, I'm going to walk you through building a governance strategy from the ground up. We'll talk about the Default Environment, maker environments, security baselines, ownership models, monitoring, observability, risk scoring - all of it.

But this won't be a checklist. It won't be "click here, enable this, you're done."

Every article will start with the *why*. Why does this decision matter? What are you optimizing for? What are the trade-offs? Then we'll talk about the *what* – what you're actually trying to achieve. And only then will we get to the *how*, the technical implementation.

In Part 1, we'll start with the Default Environment. Not because it's technically complex, but because it's your first strategic decision. How you think about the Default Environment reveals how you think about governance as a whole.

But before you get there, sit with those four questions. Write down your answers. Share them with your team. Get alignment.

Because governance doesn't start when you open the Admin Center.

It starts when you decide what you stand for.

And in the end, governance without mindset is not governance. It's just configuration 🤷‍♂️

---

I hope you liked this blog. Feel free to find me on [LinkedIn](https://www.linkedin.com/in/michaelroth42/) if you have questions, want to work with me, or just want a nice chat 😎
