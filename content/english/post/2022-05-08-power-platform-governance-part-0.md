---
title: Power Platform governance - setting the scene
description: This blog sets the scene for good power platform governance, demonstrates what patterns need to be identified for good implementation, and what should be considered technically
summary: sum This blog sets the scene for good power platform governance, demonstrates what patterns need to be identified for good implementation, and what should be considered technically
date: 'Mon, 15 Aug 2022 11:22:51 +0000'
images:
- images/blog/title-Power-Governance-Setting-Scene_2.png
author: Michael Roth
tags: 
    - Power Platform
    - Governance
    - Administration
    - Security
type: trending
draft: false
---

## Introduction to Governance blog post series

This series consists of technical articles as well as organizational considerations, such as why and how to create a good governance for Power Platform. This is equally important, because for good governance, we don't just have to look at the technology and decide what users are allowed to do and what they are not, but ask ourself, where are we actually going with this? What goal do we want to pursue and how do we get there? Or rather, what questions do we need to ask so that we can find answers to how we can get to our goal?

This is part 0 for setting the scene, in the upcoming parts, learn more about:

- Part 1: Basics
- Part 2: Environment considerations
- Part 3: Data Loss Prevention Policies & Monitoring
- Part 4: Enable Makers

## Part 0: Power Platform governance - setting the scene

### Definition of Governance

IT governance provides a framework for how tools and services should be used to establish that they are used in a way that aligns with and works towards the objectives of the organization. The goal of governance is to ensure data security and compliant use, enable efficiency, and thus empowering users to work better with tools and services.

People and their behavior will impact organizational goals, which is why tools and services are available to help users achieve them. Accordingly, a governance concept needs to be user-centric to achieve tech intensity.

In my experience, many organizations do not have a specific Power Platform governance concept at all as they did not clearly define their goals with Power Platform yet. Therefore, the rules for usage are often vague: Either they are too restrictive and leave little to no room for maneuver, or they are virtually non-existent.
Too strict rules often result in poor user adoption (and thus poor ROI) and lead to shadow IT solutions. If there are no or hardly any rules enforced, this often leads to a wild and uncontrolled sprawl of apps, poor overview and thus resulting in security gaps. Moreover, it also leads to administrators having to respond suddenly and unplanned to urgent matters.

If there's one thing I don't want, it's unplanned tasks that grab my attention directly. The less governance rules are clearly formulated, the more likely we have to step in unexpectedly to put out fires.

### What are the benefits of good Power Platform governance?

Good governance helps making the benefits of Power Platform usable in an organization:

- Reduced operating costs
- Increased productivity
- Enhanced collaboration
- Improved employee engagement

![Image that shows the benefits of the Power Platform: reduced operating costs, increased productivity, improved collaboration and improved employee engagement](/images/BenefitsOfPowerPlatform.png)

We can utilize a Power Platform governance concept to support users in making good decisions that align with corporate and IT strategic objectives.

To define our goals, we can use the following supporting questions as a guideline:

- Who shall benefit from Power Platform?

--> Citizen Developers, Code first Developers, Admin teams, or all of them?

- What is the intended scope of Power Platform?

--> Do we want to tackle personal productivity solutions or are we looking to retire legacy tools and processes?
--> Are we looking into mission critical, organization-wide solutions?

- Do we want to buy one low-code app or do we want to invest in a platform to support a long term goal?

#### Learning environment for maker

Makers need an environment in which they can learn how to use all tools of Power Platform according to rules, regulations and governance policies we set up in our tenant. Let's call it a learning environment. We will want to have the exact same rules and governance policies, which are in place in our production environment, in that learning environment as well. It's important that users experience the same working conditions across different environments, to learn how to use the tools.

If users break something in this learning environment, it can be reset. This is important for users to know, since humans learn through trial and error. Yet many organizations don't foster a culture where making mistakes is part of learning, which is why they don't encourage trial. In the learning environment, people have access to tools, are taught about the rules and how to use the tools accordingly. This is mandatory in order to teach makers how to use Power Platform for their personal and business productivity.

The difficult part with governance is, that a there is a conflict of objectives. The objective of the IT departments is to maintain the functionality and security of systems. Or in other words, to not change it (when it works). When any new tool is introduced, the objective is to change behavior for the better in order to optimize working processes. There is a conflict between keeping the status quo and changing it. Both objectives are equally valid, they just come from different areas of the organization. To get a better understanding of how to create a governance concept that maintains data security and protection on the one hand, yet enables users to experience new possibilities through low code platforms, let's have a look how governance models have often been designed and why that doesn't fully satisfy all needs.

A lot of governance models work by prohibiting access and restricting opportunities. In a classic, often outdated perception of how we work together in organizations, there is the idea of silos. According to that idea, employees work in their area and don't collaborate with people from other areas as they each have their own strategies and objectives. Following that logic, we often find governance models that only make sure achieving the objective to keep the status quo. In my experience I see organizations designing governance models to...

- maintain control,
- ensure planning certainty and
- isolate knowledge

so users can't break anything and we can ensure the stability of the system.

The idea of control, predictability and hierarchies is the main driver for this mindset, yet these concepts no longer meet the needs of modern organizations.  Accordingly, as demands on modern organizations change, so must a modern governance concept. As explained in detail in the article [Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail), it is necessary to abolish old mental models and replace them with new ones so that the benefits of Microsoft 365 and Power Platform can be leveraged by the organization.

> Same old thinking, same old problems.

The acronym VUCA describes the environments in which modern organizations operate and illustrates why we need to adapt our ways of thinking: These environments are volatile, uncertain, complex and ambiguous.

**Volatility:** The world is changing faster than ever before, BUT the world will never change as slowly as it is right now. In other words, the pace of change will continue to increase. New challenges, competitors, and different unpredictable factors are something we have to deal with. That means that long term planning and the reliability of this planning won't be sufficient for modern organizations.

**Uncertainty:** Predictability and calculability of events are rapidly decreasing; forecasts and experiences from the past due to shaping the future are losing their validity and relevance. Just look at how quickly and comprehensively COVID-19 changed the way we work. Do we have to say more?

**Complexity:** We live in a complex and connected world with various connections that are difficult to keep track of, making it challenging to clearly define cause and effect. The world is not just complicated; it's complex.

**Ambiguity:** The aspects described above make it clear that decisions today are no longer straightforward. 'One size fits all' is rarely a suitable model anymore. It is often not a question of WHAT, but of HOW and WHY. This leads to the fact that the demands on organizations today are paradoxical, sometimes even contradictory.

> In an ever-changing environment, a strategy based on inflexibility can never be successful.

Let's have a look and compare old and new mental models and how the old models need to change:

- Controlling --> Empowerment
- Planning --> Experimentation
- Privacy --> Transparency

I will use the [iceberg model](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail#defining-the-iceberg-model) to illustrate this, as it makes it easier to understand which structures, patterns, and mental models lead to certain behaviors. The iceberg model helps us look behind the events we can perceive. We look at events that are based on patterns, that are favored by structures, that are grounded on mental models. We need to focus on the root causes of events to change user behavior sustainably.

I'll start with a real-world example of a company struggling to increase user adoption. As a result, Power Platform could not be sustainably implemented in the company, which led to neither the expected benefits nor the expected ROI being achieved.

#### Power Platform Governance - Old world

**Level 1 - What just happened? (Event)**: Bad user adoption for Power Platform, growing Shadow IT

**Level 2 - What happened over time? (Pattern)**: Users trying to work with the platform but don't understand it, get no proper support, bumping up against limits over and over, decreasing usage, dissatisfaction

**Level 3 - Which system supports and influences these patterns? (Structure)**: A very restricted governance model is in place in order to secure data, while lack of training and empowerment, poor understanding of benefits of Power Platform

**Level 4 - Which values, beliefs and assumptions shape the system and keep it in place? (Mental Model)**: *Never change a running system* but protect it against immature users.

With our considerations behind a governance concept, we can make people aware of the broken system that doesn't meet the needs anymore, and that forces people into workarounds, unhealthy work ethics, and poor connection to their organization.

> Stop trying to fix users when we need to fix the system.

In order to change the outcome on the event level, we need to change our mental model first. To make it easier, I will turn the iceberg model upside down:

#### Power Platform Governance - New world

**Level 4 - Which values, beliefs and assumptions shape the system and keep it in place? (Mental Model**: In order to benefit from Power Platform, we need to first define and communicate our objectives with Power Platform so that we can then empower users, give them opportunity and room to safely experiment and make their efforts transparent so others can learn from that.

**Level 3 - Which system supports and influences these patterns? (Structure)**: A modern governance model helps users making the right decisions. It creates a learning environment for makers to experiment and improve.

**Level 2 - What happens over time? (Pattern)**: Users enjoy to use the platform, exchange ideas, celebrate success.

**Level 1 - What just happens? (Event)**: Utilization of Power Platform and multiple apps and workflows automate business processes to gain benefits of the platform.

To balance the valid needs of admins who secure and maintain data access, overall security and keep systems working with the emerging needs of business being more closely involved into automating workloads and bringing solutions to life, we need to put our own mindset and mental models to the test. To do this, it is helpful to clarify which goals we want to achieve with implementing Power Platform. Only when we know where we want to go, we can define the necessary steps 🙂

### What's needed to create good Power Platform governance

Every organization needs to determine what good governance looks like depending on their unique requirements. Determining factors are:

- Architecture of IT landscape
- Structure of the organization
- Corporate culture
- Goals and strategies

This is why no one can impose good governance from the outside or apply a best-practice blueprint. Even advanced or elaborated concepts need to be adapted to an organization, otherwise they won't paint a coherent picture. In that case it would lead to either users trying to circumvent the governance concept because it was too restrictive or to security gaps because it has only been cared for too laxly.

To get started, there are a few things that should be considered: Each category consists of its own articles, which helps us to understand the different aspects to create a good basis for governance.

#### Basics

- [Designate Power Platform Admin](https://www.michaelroth42.com/post/2022-05-24-power-platform-administrator/)
- [Think about limiting environment creation](https://www.michaelroth42.com/post/2022-05-24-think-about-limiting-environment-creation/)
- [Disable Self-service](https://www.michaelroth42.com/post/2022-09-14-disable-self-service/)

#### Environment considerations

- [Take care of your default environment](https://www.michaelroth42.com/post/2022-07-02-take-care-about-your-default-environment/)
- [Think about a minimal set of environments](https://www.michaelroth42.com/post/2022-07-03-think-about-a-minimal-set-of-environments/)
- [Set up Security groups](https://www.michaelroth42.com/post/2022-07-03-set-up-security-groups-for-your-environments/)

#### Data Loss Prevention Policies & Monitoring

- Consider a DLP strategy
- Monitoring Power Platform activities

#### Enable Makers

- Welcome Makers
- Explain the rules
- Give guidelines and best practices
- Create Communities
- Trainings

I will highlight all aspects in each category with a separate article, stay tuned.

---

[Let me hear from you](https://twitter.com/MichaelRoth42/status/1561989243626524672?s=20&t=k2aAt4MPkCh328u0EtImBQ)
I welcome comments, remarks and discussions about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

## Useful resources

[Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail)

[Iceberg model](https://glowconsulting.com/wp-content/uploads/2018/04/Iceberg-model_Glow_Mar18.pdf)

[Microsoft 365 Maturity model](https://docs.microsoft.com/microsoft-365/community/microsoft365-maturity-model--intro)

[Power Platform Adoption workbook](https://aka.ms/powerplatformadoptionworkbook)

---

[Photo in header image by Viktor Bystrov](https://unsplash.com/photos/tXIpcZhVKiQ)