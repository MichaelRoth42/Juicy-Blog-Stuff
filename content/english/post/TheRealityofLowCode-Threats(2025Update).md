---
title: The Reality of Low-Code Threats (2025 Update)
description: Low-code is powerful, but not harmless. Learn how misconfigurations and weak controls turn Power Platform apps into 2025’s hidden security risks.
date: '2025-09-10T07:11:06.185Z'
images: 
- images/blog/title-The-Reality-of-Low-Code-Threats.png
author: "Michael Roth"
tags:
  - Tech
  - PowerPlatform
  - Administration
  - Governance
  - PowerApps
  - SharePoint
  - Microsoft
  - Security
type: regular
draft: true
---

# The Reality of Low-Code Threats (2025 Update)

> **OWASP LCNC Reference:** #️⃣ 4 – Security Misconfiguration  
> *(Based on the OWASP Top 10 for Low-Code/No-Code Applications, 2022–2025)*  
> [OWASP LCNC Top 10](https://owasp.org/www-project-top-10-low-code-no-code-security-risks/)

---

## 🎯 Introduction – Why This Matters

“Low-code means low risk.”  
I have heard that sentence far too often, and every time, a security engineer somewhere screams quietly into a pillow.  

Low-code isn’t magic. It’s software. And every piece of software can be misconfigured, exposed, or abused.  
In 2025, the Power Platform is in more enterprises than ever, but most organizations still treat it like a sandbox for small productivity apps.  
Attackers, however, don’t care if your app was built by a citizen developer or a professional coder.  
If it holds data, it’s a target.  

This article kicks off the *Power Platform Security 2025* series by exploring what “threats” actually look like in a low-code world and why governance isn’t the fun police, but your last line of defense.

### About OWASP LCNC

Throughout this series, I’ll refer to the [OWASP Top 10 for Low-Code/No-Code Security Risks](https://owasp.org/www-project-top-10-low-code-no-code-security-risks/).  
OWASP is an independent non-profit that defines global security best practices – think of it as the ISO standard for web and app security.  
It’s the perfect baseline to translate traditional cybersecurity principles into the low-code world.  
At the top of every blog, you’ll find a short OWASP reference, a simple marker that ties each risk back to a universal security principle. It keeps us honest, grounded, and just the right amount of paranoid 🙃

---

## 🧩 Understanding the Risk

The biggest risk in Power Platform isn’t hacking, it’s **trusting defaults**.  

Security misconfiguration happens when you assume the platform has you covered. And you can't blame Microsoft for not taking care of your platform. They give you all the possibility, yet the default settings, are pretty open and may lead to unhealth practices (or why else do they recommend to [rename the default environment](https://learn.microsoft.com/en-us/power-platform/guidance/adoption/secure-default-environment#rename-the-default-environment)?😉)

So, every environment, every connector, every data source brings its own risk surface.  
When everything is connected through Microsoft 365, one loose permission or public API endpoint can turn into a full-blown data leak.  

Typical misconfigurations include  
• Publicly shared Power Apps with “Everyone in the organization” access  
• Anonymous Power Pages exposing OData feeds  
• DLP policies not enforced or scoped too broadly (or my favourite: custom connectors available everywhere)  
• Makers storing secrets directly in Canvas Apps (yes, it happens)  
• Admins allowing unreviewed connectors in production environments  

---

## 🔍 How It Appears in Power Platform

Security misconfiguration in Power Platform is silent but deadly.  
You won’t see flashing alerts or pop-ups. Everything works fine – until someone outside your intended audience sees data they shouldn’t.  

![Real World example 2021](/images/SecurityThreats_1.jpg)

Real-world example (2021):  
A series of Power Apps portals leaked 38 million records because their OData APIs were set to public by default.  
No malware. No hacker genius. Just default settings.  
[UpGuard Report – Microsoft Power Apps Exposure](https://www.upguard.com/breaches/power-apps)  

In 2025, the same logic applies, except now with AI, connectors, and Copilots in the mix.  
Every new feature adds another attack surface – another place to forget a checkbox.

---

## 🧠 How Cyber Attacks Actually Work

Before we dive into each risk, let’s level-set.  
A cyber attack isn’t a movie scene where someone types fast in a dark room.  
It’s a sequence of **vectors**: entry points an attacker can use to reach their goal.  
A vector might be a vulnerable API, a misconfigured permission, or a well-crafted phishing email that makes someone click.  
The technical part is rarely the problem. The weak spot is usually human trust and configuration.  

That’s why OWASP’s Low-Code/No-Code Top 10 is so relevant.  
It doesn’t list Hollywood-style hacks, it lists the real mistakes that make systems fall apart.

This series follows those attack vectors one by one, so both makers and admins can learn to recognize them and build good habits around each.  
The goal isn’t fear, but it’s competence 🤓 

---

## ⚙️ Misconfiguration vs “Real Hacks”

When people imagine a cyber attack, they think of ransomware or nation-state hackers. And don't get me wrong, I don't want to belittle or downplay these techniques. It's just that far more “hacks” start with something mundane. And almost every time, the “human” element is an important part of it.  
Phishing emails, reused passwords, or a portal left open to the internet.  

According to the latest reports, roughly **two thirds** of breaches involve the human element and about **one quarter** start with plain mistakes.  
([Verizon DBIR 2024](https://www.verizon.com/business/resources/reports/2024-dbir-data-breach-investigations-report.pdf), [IBM Cost of a Data Breach 2024](https://www.ibm.com/think/insights/cost-of-a-data-breach-2024-financial-industry))

So no, it’s not the hackers in hoodies you should fear, it’s the checkbox you forgot to uncheck. Or the untrained citizen developer, because low-code “isn't that complicated,” “anyone can do it.” 

---

## 🧩 What This Series Will Do

Each article in *Power Platform Security 2025* focuses on one common attack vector defined by OWASP.  
You’ll learn what it is, how it shows up in Power Platform, and what to do about it.  
Makers will learn how to spot risky situations and why certain controls matter so they can make safer choices without needing a security handbook.  
Admins will get actionable policies to configure secure environments.  
Together, these habits can eliminate most of the risks before an attacker even shows up.  

By the end of this series, you should be able to look at any app or environment and spot the holes before someone else does.  

That’s not paranoia. That’s professionalism 😎

---

## 🧾 References and Further Reading

- [OWASP Top 10 for Low-Code/No-Code Security Risks (2022–2025)](https://owasp.org/www-project-top-10-low-code-no-code-security-risks/)
- [UpGuard Report – Microsoft Power Apps Data Exposure (2021)](https://www.upguard.com/blog/microsoft-power-apps-data-exposure)
- [Verizon Data Breach Investigations Report 2024 (DBIR)](https://www.verizon.com/business/resources/reports/dbir/)
- [IBM Cost of a Data Breach Report 2024](https://www.ibm.com/reports/data-breach)
- [Microsoft Learn – Power Platform Security Guidance](https://learn.microsoft.com/en-us/power-platform/admin/security)
- [Microsoft Purview Audit Documentation](https://learn.microsoft.com/en-us/purview/audit-log-search)
- [Microsoft Sentinel Integration for Power Platform](https://learn.microsoft.com/en-us/azure/sentinel/power-platform)

---

Find me on [LinkedIn](https://www.linkedin.com/in/michaelroth42/) if you have questions, want to work with me, or just want a nice chat.

For a full overview of this series, visit the **[Power Platform Security 2025 Hub](https://www.michaelroth42.com/post/security-2025-hub)** *(coming soon!)*

---

**Next:** [Power Platform Security Levels – Understanding Roles and Boundaries](https://www.michaelroth42.com/post/2022-08-26-power-platform-security-levels/)


