---
title: What is good Power Platform Governance
description: This blog asks what good power platform governance is, what patterns need to be identified for good implementation, and what should be considered technically
date: '2022-05-26T20:34:32.391Z'
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: true
---


## Introduction to Governance blog post series

In addition to a basic understanding, I want to provide guidance and questions that will help create good governance. This series consists of technical articles as well as organizational considerations, such as why and how. This is equally important, because for good governance, you don't just have to look at the technology and decide what users are allowed to do and what they are not, but ask yourself, where are we actually going with this? What goal do we want to pursue and how do we get there? Or rather, what questions do we need to ask so that we can find answers to how we can get to our goal?

This is part 0 for setting the scene, in the upcoming parts, learn more about:

- part 1: Basics
- part 2: Environment considerations
- part 3: DLP policies
- part 4: Monitoring
- part 5: Maker enablement

---- Let's get started

## Definition of Governance

I would like to start by briefly clarifying what IT governance is good for in companies.
IT governance provides a framework for how tools and services should be used. This framework serves to ensure that the tools and services are used in such a way that they contribute to the goals of the organization. It also aims to ensure security and efficient use.
Governance, then, is something that relates directly to user behavior.
Users and their behavior should also impact organizational goals, so tools and services are available to help users better realize them.
So governance is about ensuring data security, ensuring compliant use, enabling efficiency, and thus enabling users to work better with tools and services.

Accordingly, a governance concept should always closely involve the user.

>A good governance develops a thriving and engaging usage around Power Platform in order to achieve tech intensity.

Many organizations do not have a Power Platform Governance concept at all. And this is often due to the fact that there are no clearly defined Power Platform goals. Therefore, the rules for governance are often vague: Either they are too restrictive and leave little to no room for maneuver, or they are virtually non-existent.
Too hard governance rules often result in poor user adoption (and thus poor ROI) and lead to shadow IT solutions.
If there are no rules or hardly any rules implemented, this often leads to a wild growth of apps, little overview and resulting security gaps.

The Power Platform is complex, so it is not easy to create a good concept, but it is worth it. To make this clear, I will answer two questions in this blog.

//work over
## What are the benefits of good Power Platform governance?

Good governance helps making the benefits of Power Platform usable in a company. This is what we actually want when we think about integrating Power Platform into our company:

{{< image src="images/blog/BenefitsOfPowerPlatform.png" >}}

Every organization needs to determine what good governance looks like depending on their unique requirements. Determining factors are the architecture of IT landscape, structure, corporate culture, goals and strategies of an organization, which is why no one can impose good governance from the outside.
Even advanced or elaborated concepts needs to be adapted to an organization, otherwise it won't paint a coherent picture.

In that case it would lead to either users trying to circumvent the governance because it was too restrictive or to security gaps because it has only been cared for too laxly.

We will utilize the Power Platform governance concept to support users in making good decisions that align with corporate and IT strategic objectives.

To define our goals, we can use the following supporting questions as a guideline

- Who shall benefit from Power Platform? Citizen Developers, Code first Developers, Admin teams, or all of them?
- What is the intended scope of Power Platform (Do we want to tackle personal productivity solutions or are we looking to retire legacy tools and processes? Or are we looking into mission critical, organization-wide solutions)
- Do we want to buy a low-code app or do we want to invest in a platform?

We can identify four goals of Power Platform - Don't get me wrong, you can achieve all of them, but you should know where to start to not get overwhelmed.

>Don't Half-Ass multiple Things, Whole-Ass THE Thing

Set a smart goal, then track your progress with success criteria as you go along (hint: the [Power Platform Adoption workbook](https://aka.ms/powerplatformadoptionworkbook) has a few awesome resources to help you with that).

### Safe space for maker

I often talk about a term I call safe space for makers and I'd like to explain what I mean by that. Maker need an environment in which they can learn how to use all the tools of Power Platform according to the rules, regulations and governance policies you have in your tenant. 
That means that the exact same rules, regulations and governance policies which are in place in your production environment have to be in that safe place as well. Otherwise you don't learn the rules. Otherwise you're just playing.

The point is, that if user break something in this safe space, it can be reset. This is important for the user to know. People learn through trial and error and many organizations don't want errors, so they forbid trial in the first place. That's not how learning takes place.

In this environment, people have access to the tools, are taught about the rules and how to use the tools accordingly. This is mandatory in order to teach makers how to use Power Platform for their personal productivity and for business productivity alike.

A lot of governance models are still used to prohibit access and possibilities, to shut down and restrict opportunities. This comes out of an outdated understanding of the capabilities of users and creates an IT vs Business mentality.

As a result, you often find models that are designed to ensure...

- Maintain control,
- Ensure planning certainty and
- isolate knowledge.

This is often substantiated by the fact that this is necessary to maintain data security and protection. Which is important, but the idea of how to achieve this is often a very outdated idea: Control, predictability, and hierarchies no longer meet the needs of modern organizations; accordingly, as the demands on modern organizations changes, so must the demands on a modern governance concept. As explained in detail in the article [Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail), it is necessary to abolish old mental models and replace them with new ones so that the benefits of Microsoft 365 and the Power Platform can be experienced by the users.

I will give an example of old mental models and their modern equivalent:

- Controlling > Empowering
- Planning > Experimentation
- Privacy > Transparency

To illustrate this, I would like to use the [iceberg model](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail#defining-the-iceberg-model). This makes it easy to understand which mental models, patterns and structures lead to certain behaviors. So if you want to create a governance that helps users to make the right decisions, it is necessary to create the right foundations.
I'll start with a real-world example of a company struggling to increase user adoption. As a result, the Power Platform could not be sustainably implemented in the company, which led to neither the expected benefits nor the expected ROI being achieved.

### Power Platform Governance - Old world

**Level 1 - Event**: Bad user adoption for Power Platform, growing Shadow IT

**Level 2 - Pattern**: Users trying to work with the platform but don't understand it, bumping up against limits again and again, utilization of unauthorized 3rd party tools

**Level 3 - Structure**: A very restricted governance model is in place in order to secure data

**Level 4 - Mental Model**: User don't know their way around data, therefore we should Power Platform down, so user don't break things

Now what can we now do about it? With our considerations behind a governance concept, we can make people aware of the broken system that doesn't meet the needs anymore, and that forces people into workarounds, unhealthy work ethics, and poor connection to their organization.

> Please stop trying to fix users when we need to fix this system.

If we want to get a different event or outcome, we have to work on the underlying issue, the root of the problem. In order to change the outcome on the event level, we have to change our mental model first.
To make it easier, I will turn the iceberg model upside down:

### Power Platform Governance - New world

**Level 4 - Mental Model**: In order to benefit from Power Platform, we need to empower our users, give them opportunity and room to safely experiment and make their efforts transparent so others can learn from that.

**Level 3 - Structure**: A modern Governance model is in place in order to help users make the right decisions. It creates a safe space for makers to experiment and learn.

**Level 2 - Pattern**: Users like to use the platform, exchange ideas, celebrate success.

**Level 1 - Event**: Utilization of Power Platform and multiple apps and workflows automate the business to gain the benefits of the platform.

I hope that helps to answer the first question "How can good governance contribute to this? Or also, why should I care?".
So before we turn to the content of good governance, we urgently need to put our own mindset or mental model to the test. To do this, it is helpful to clarify what goals you want to achieve with the Power Platform. Only when you know where you want to go can you define the necessary steps 🙂

## What's needed to create a good Power Platform governance?

Let's turn to the second question, what belongs in good governance?

As mentioned earlier, there is not one good governance that works for different organizations. The architecture of the IT landscape, the setup, the work culture, goals and strategies of the organization, these are all determining factors, so no one can just slap good governance on it from the outside.

But there are a few things that should be considered at a minimum, which I have grouped into the following categories. Each category consists of its own articles, which should help to understand the different aspects in order to create a good basis for governance.

### Basics

- Designate Power Platform Admin
- Think about limiting environment creation
- Switch on tenant isolation
- disable self service

### Environment considerations

- Take care about your default environment
- think about an mvp set of environments
- security groups

### Data Loss Prevention Policies

- Layering DLPs
- Connector action control & endpoint filtering
- PowerShell possibilities

### Monitoring whats going on

- Enable Activity logs
- CoE Possibilities

### Enable Maker

- Welcome Maker
- Explain the rules
- Give guidelines and best practices
- Create Communities
- Trainings

I will highlight all aspects in each category with a separate article and I will try to publish them as soon as possible. I welcome comments, remarks and discussions about your experiences with Power Platform Governance, if I forgot something and what I can do better 🙂

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Useful resources

[Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail)

[Iceberg model](https://glowconsulting.com/wp-content/uploads/2018/04/Iceberg-model_Glow_Mar18.pdf)

[Microsoft 365 Maturity model](https://docs.microsoft.com/microsoft-365/community/microsoft365-maturity-model--intro)
