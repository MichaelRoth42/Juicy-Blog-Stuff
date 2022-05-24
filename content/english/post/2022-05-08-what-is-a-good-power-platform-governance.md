---
title: What is a good Power Platform Governance
description: This blog asks the questions "What makes for good governance?" and how do we
  create one?
date: 2022-05-09T15:00:09.925Z
author: ""
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: true
---

# What is a good Power Platform Governance

When we talk about Power Platform Governance we need to set the scene to describe what is meant by Governance.

## Definition of Governance

According to Gartner, IT Governance is defined as the processes that ensure the effective and efficient use of IT in enabling an organization to achieve its goals. In order to do so, governance concepts have a number of objectives to ensure the demand-side and the supply-side of IT processes:

- fits the overall strategy
- risk mitigation
- data security
- connects IT and business
- enables Maker to achieve more
- helps with good decision making
- enables IT to create value that fits into overall business strategy
- ROI of IT decisions

The clue is, that a good governance should always consider the user and make them a cornerstone in developing the governance.

> Core idea: Governance and adoption are very closely intertwined and empowers users. If you think about governance, you have to think about users. Create safe space for all makers in order to develop a thriving and engaging usage around Power Platform in order to achieve tech intensity.

I often experience that a lot of organizations don't have a governance concept in place considering Power Platform. I think this is because the very core nature of the Platform: bringing maker and code first developer together with low-code.
In order to help setting up a good governance I will cover two main questions in this blog:

1. What are the benefits of good power platform governance? Aka why should you care?
2. What's needed to create a good Power Platform governance?

## What are the benefits of good power platform governance?

Good governance helps to make the benefits of the Power Platform usable in the company. This is what we actually want when we think about integrating the Power Platform into our company.

{{< image src="images/blog/BenefitsOfPowerPlatform.png" >}}

{{< image src="https://github.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/assets/images/blog/BenefitsOfPowerPlatform.png" >}}

Everyone must determine for themselves what good governance looks like and it always depends on the organization. The architecture of the IT landscape, the structure, the working culture, the goals and strategies of the organization, all these are determining factors, so no one can simply impose good governance from the outside.
It must always be adapted to the organization, otherwise it won't paint a coherent picture. (This leads to users trying to circumvent the governance because it is too restrictive or to security gaps because it has only been cared for laxly).

In addition to a basic understanding, I want to provide guidance and questions that will help create good governance. This series consists of technical articles as well as organizational considerations, such as why and how. This is equally important, because for good governance, you don't just have to look at the technology and decide what users are allowed to do and what they are not, but ask yourself, where are we actually going with this? What goal do we want to pursue and how do we get there? Or rather, what questions do we need to ask so that we can find answers to how we can get to our goal?

How can we use governance to create a framework for all stakeholders that increases the likelihood that they will make good decisions. Good decisions are those that lead us to reach our goal (which we should have defined beforehand).

### Safespace for maker

If we want to have what Microsoft promises us from the use of the Power Platform (Citizen Developer, everybody is a maker, less confusion, more focus on what matters, better collaboration, purpose in work, belonging, etc), if we want to promote such a work culture, then we have to help the users to achieve it. We do this by using governance to create an environment in which we increase the likelihood that users can make the right decisions. Decisions that lead to a good outcome.
What are decisions that lead to a good outcome, that lead to a positive use of the platform, to more collaboration and less "being busy" and more "productive". We can lead our users to be more likely to make these decisions, but to do that we need to understand that our goal is to have a modern understanding of organizational work.

Governance is often used in organizations that are structured in a now-outdated model (for more on this, see [Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail)). As a result, many governance considerations are still intended to:

- Maintain control,
- Ensure planning certainty,
- isolate knowledge.
  
This is often underpinned by the fact that this is necessary to maintain data security and protection. It is often assumed that the business world as we know it from the last 40 years still exists. But that's not the case, because to put it succinctly: Control, predictability, and hierarchies no longer meet the needs of modern organizations; accordingly, as the demands on governance change, so must the demands on modern organizations. As explained in detail in the article [Why Microsoft 365 adoption projects fail](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail), it is necessary to abolish old mental models and replace them with new ones so that the benefits of M365 and the Power Platform can be lived by the users.

Old mental models and their modern equivalent:

- Controlling > Empowering
- Planning > Experimentation
- Privacy > Transparency

To illustrate this, I would like to use the [iceberg model](https://docs.microsoft.com/microsoft-365/community/why-m365-adoption-projects-fail#defining-the-iceberg-model). This makes it easy to understand which mental models, patterns and structures lead to certain behaviors. So if you want to create a governance that helps users to make the right decisions, it is necessary to create the right foundations.
I'll start with a real-world example of a company struggling to increase user adoption. As a result, the Power Platform could not be sustainably implemented in the company, which led to neither the expected benefits nor the expected ROI being achieved.

**Power Platform Governance - Old world**

**Level 1 - Event**: Bad user adoption for Power Platform, growing Shadow IT

**Level 2 - Pattern**: Users trying to work with the platform but don't understand it, bumping up against limits again and again, utilization of unauthorized 3rd party tools

**Level 3 - Structure**: A very restricted governance model is in place in order to secure data

**Level 4 - Mental Model**: User don't know their way around data, therefore we should Power Platform down, so user don't break things

*"What can we now do about it? Make people aware of the broken system that doesn't meet our needs anymore, and that forces people into workarounds, unhealthy work ethics, and poor connection to their organization.* 

> Please stop trying to fix users when we need to fix this system.

If we want to get a different event or outcome, we have to work on the underlying issue, the root of the problem. In order to change the outcome on the event level, we have to change our mental model first.
To make it easier, I will turn the iceberg model upside down:

**Power Platform Governance - New world**

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

//consider the questions "Why would you want that?" in every blog and bring it back to the core idea of governance

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
