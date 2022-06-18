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

- Part 1: Basics
- Part 2: Environment considerations
- Part 3: DLP policies
- Part 4: Monitoring
- Part 5: Maker enablement

---- Let's get started

## Definition of Governance

I will start by briefly clarifying how organizations can benefit from IT governance.

IT governance provides a framework for how tools and services should be used. This framework contributes to ensuring that tools and services are used in a way that they align with and work towards the objectives of the organization. It also aims to establish security and efficient usage.
Thus, governance relates directly to user behavior.
Users and their behavior will impact organizational goals, which is why tools and services are available to help users better implement them.
In essence, governance is about ensuring data security, ensuring compliant use, enabling efficiency, and thus enabling users to work better with tools and services.

Accordingly, a governance concept needs to be user-centric.

>A good governance develops a thriving and engaging usage in order to achieve tech intensity.

In my experience, many organizations do not have a specific Power Platform Governance concept at all as they did not clearly define their goals with Power Platform. Therefore, the rules for governance are often vague: Either they are too restrictive and leave little to no room for maneuver, or they are virtually non-existent.
Too strict governance rules often result in poor user adoption (and thus poor ROI) and lead to shadow IT solutions.
If there are no or hardly any rules enforced, this often leads to a wild and uncontrolled growth of apps, poor overview and thus resulting security gaps.

## What are the benefits of good Power Platform governance?

Good governance helps making the benefits of Power Platform usable in an organization:

- Reduced operating costs
- Increased productivity
- Enhanced collaboration
- Improved employee engagement

{{< image src="images/blog/BenefitsOfPowerPlatform.png" >}}

We will utilize the Power Platform governance concept to support users in making good decisions that align with corporate and IT strategic objectives.

To define our goals, we can use the following supporting questions as a guideline

- Who shall benefit from Power Platform?

*Citizen Developers, Code first Developers, Admin teams, or all of them?*

- What is the intended scope of Power Platform

*Do we want to tackle personal productivity solutions or are we looking to retire legacy tools and processes?*

*Are we looking into mission critical, organization-wide solutions)*

- Do we want to buy one low-code app or do we want to invest in a platform?

### Safe space for maker

I often talk about a term I call safe space for makers and I'd like to explain what I mean by that. Makers need an environment in which they can learn how to use all the tools of Power Platform according to the rules, regulations and governance policies you have in your tenant.
That means that the exact same rules, regulations and governance policies which are in place in your production environment have to be in that safe place as well. 
It's important that user experience the same working conditions across different environments, in order to learn how to use the tools. 

The point is, that if user break something in this safe space, it can be reset. This is important for the user to know. People learn through trial and error and many organizations don't want errors, so they forbid trial in the first place. That's not how learning takes place.

In this environment, people have access to the tools, are taught about the rules and how to use the tools accordingly. This is mandatory in order to teach makers how to use Power Platform for their personal productivity and for business productivity alike.

The difficult part with governance is, that a there is a conflict of objectives. The objective of the IT department is, to maintain the functionality and security of the system, to keep the status quo. 
When any new tool is introduced, the objective is to change behaviour for the better in order to optimize working processes. There is a conflict between keeping the status quo and changing it. Both objectives are equally valid, they just come from different areas of the organization. 
In order to understand how to create a governance that maintains data security and protection on the one hand, yet enables users to experience new possibilities to develop business processes through low code platforms, we need to ask ourselves how governance models have often been designed.

A lot of governance models are still used to prohibit access and possibilities, to shut down and restrict opportunities. This comes out of an outdated understanding of the capabilities of users and creates an IT vs Business mentality.

In a classic, often outdated perception of how we work together in organizations, there is the idea of silos. Employees work in their area and don't really collaborate with people from other areas. They each have their own goals, strategies and objectives. Following that logic, we often find governance models that make sure to achieve the objective to keep the status quo. We do that by designing governance models to...

- maintain control,
- ensure planning certainty and
- isolate knowledge so the user can't break anything and we can ensure the stability of the system.

As I said, this is the logical consequence from an old understanding of how organizations work. The concept of control, predictability and hierarchies are the main drivers for this mindset, yet these concepts no longer meet the needs of modern organizations; accordingly, as the demands on modern organizations change, so must the demands on a modern governance concept. As explained in detail in the article [Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail), it is necessary to abolish old mental models and replace them with new ones so that the benefits of Microsoft 365 and Power Platform can be leveraged by the organization.

Before I make a clear comparison of old and new mental models, I want to give a little insight into why old thinking cannot solve new problems (or also: why we have to adapt our thinking)

The acronym VUCA describes the environment in which modern organizations operate: These environments are volatile, uncertain, complex and ambiguous

**_NOTE:_**<br>
**Volatility:** The world is changing faster than ever before, BUT the world will never change as slowly as it is right now. In other words, the pace of change will continue to increase. New challenges, competitors, and different unpredictable factors are something we have to deal with. That means that long term planning and the reliability of this planning won't be sufficient for modern organizations.

**Uncertainty:** Predictability and calculability of events are rapidly decreasing; forecasts and experiences from the past due to shaping the future are losing their validity and relevance. Just look at how quickly and comprehensively COVID-19 changed the way we work. Do we have to say more?

**Complexity:** We live in a complex and connected world with various connections that are difficult to keep track of, making it challenging to clearly define cause and effect. The world is not just complicated; it's complex.

**Ambiguity:** The aspects described above make it clear that decisions today are no longer straightforward. 'One size fits all' is rarely a suitable model anymore. It is often not a question of WHAT, but of HOW and WHY. This leads to the fact that the demands on organizations today are paradoxical, sometimes even contradictory.

---

> In an ever-changing environment, a strategy based on inflexibility can never be successful.

Now as we can see, old mental models can't succeed in a modern organization, so let's have a look and compare old and new mental models:

- Controlling --> Empowerment
- Planning --> Experimentation
- Privacy --> Transparency

I will use the [iceberg model](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail#defining-the-iceberg-model) to illustrate this, as it makes it easier to understand which structures, patterns, and mental models lead to certain behaviors. The iceberg model helps us look behind the events we can perceive. So we look at events that are based on patterns that are favored by structures that are based on mental models. So with the iceberg model we can filter out the root causes of certain events. 
We can only change user behavior in the long term and sustainably if we work on the causes, the mental models.

If you want to create a governance concept that helps users making the right decisions and to increase security, it is necessary to create the right foundation.

I'll start with a real-world example of a company struggling to increase user adoption. As a result, Power Platform could not be sustainably implemented in the company, which led to neither the expected benefits nor the expected ROI being achieved.

### Power Platform Governance - Old world

**Level 1 - What just happened? (Event)**: Bad user adoption for Power Platform, growing Shadow IT

**Level 2 - What happened over time? (Pattern)**: Users trying to work with the platform but don't understand it, get no proper support, bumping up against limits over and over, decreasing usage, dissatisfaction

**Level 3 - Which system supports and influences these patterns? (Structure)**: A very restricted governance model is in place in order to secure data while, lack of training and empowerment, poor understanding of benefits of Power Platform

**Level 4 - Which values, beliefs and assumptions shape the system and keep it in place? (Mental Model)**: Never change a running system but protect it against immature users.

Now what can we now do about it? With our considerations behind a governance concept, we can make people aware of the broken system that doesn't meet the needs anymore, and that forces people into workarounds, unhealthy work ethics, and poor connection to their organization.

> Stop trying to fix users when you need to fix the system.

In order to change the outcome on the event level, we need to change our mental model first. To make it easier, I will turn the iceberg model upside down:

### Power Platform Governance - New world

**Level 4 - Which values, beliefs and assumptions shape the system and keep it in place? (Mental Model**: In order to benefit from Power Platform, we need to empower users, give them opportunity and room to safely experiment and make their efforts transparent so others can learn from that.

**Level 3 - Which system supports and influences these patterns? (Structure)**: A modern governance model helps users making the right decisions. It creates a safe space for makers to experiment and learn.

**Level 2 - What happens over time? (Pattern)**: Users like to use the platform, exchange ideas, celebrate success.

**Level 1 - What just happens? (Event)**: Utilization of Power Platform and multiple apps and workflows automate the business processes to gain benefits of the platform.

To balance the valid needs of admins who secure and maintain data access, overall security and keep systems working with the emerging needs of business being more closely involved into automating processes and bringing solutions to life, we need to put our own mindset and mental model to the test. To do this, it is helpful to clarify which goals you want to achieve with implementing Power Platform. Only when you know where you want to go can you define the necessary steps 🙂

## What's needed to create a good Power Platform governance?

Every organization needs to determine what good governance looks like depending on their unique requirements. Determining factors are:

- Architecture of IT landscape
- Structure of the organization
- Corporate culture
- Goals and strategies

This is why no one can impose good governance from the outside or apply a best-practice blueprint. Even advanced or elaborated concepts need to be adapted to an organization, otherwise they won't paint a coherent picture. In that case it would lead to either users trying to circumvent the governance because it was too restrictive or to security gaps because it has only been cared for too laxly.

To get started, there are a few things that should be considered: Each category consists of its own articles, which helps you understand the different aspects to create a good basis for governance.

### Basics

- Designate Power Platform Admin
- Think about limiting environment creation
- Switch on tenant isolation
- Disable Self-service

### Environment considerations

- Take care of your default environment
- Think about an minimal set of environments
- Set up Security groups

### Data Loss Prevention Policies

- Layering DLPs
- Connector action control & endpoint filtering
- PowerShell possibilities

### Monitoring what's going on

- Enable Activity logs
- What's possible with Center of Excellence Starter Kit

### Enable Makers

- Welcome Makers
- Explain the rules
- Give guidelines and best practices
- Create Communities
- Trainings

I will highlight all aspects in each category with a separate article, stay tuned.

// TODO tweetlink 
I welcome comments, remarks and discussions about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Useful resources

[Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail)

[Iceberg model](https://glowconsulting.com/wp-content/uploads/2018/04/Iceberg-model_Glow_Mar18.pdf)

[Microsoft 365 Maturity model](https://docs.microsoft.com/microsoft-365/community/microsoft365-maturity-model--intro)

[Power Platform Adoption workbook](https://aka.ms/powerplatformadoptionworkbook)
