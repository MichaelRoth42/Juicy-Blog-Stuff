---
title: What every Admin needs to know
description: There are a few things that every admin should know, but that no one teaches you. Don't worry, we're here for you 
date: '2024-03-18T08:11:06.185Z'
images: 
- images/blog/title-What-Every-Admin.png
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
type: regular
draft: true
---

Before [Craig](https://platformsofpower.net/) and I deep dive into the really cool stuff about administering and governing Power Platforms, we wanted to start with some regular knowledge for administrators. Becoming a Power Platform Administrator is sometimes very easy and even happens by the way. You are known in the company for being interested in the Power Platform, you are in the wrong meeting at the wrong time and boom: you are a Power Platform Administrator. 

There's a good chance that you have no idea how to behave as an admin and that can be dangerous. You probably have a lot of responsibilities and tasks to manage. You also have a lot of power and access to sensitive data and resources. That's why you need to be careful and smart about how you use your privileges and protect your accounts.

So, in this first overview article, we want to familiarize you with a few basic skills that many people are unfortunately not taught. Unfortunately, there are hardly any crash courses "So you want to be an admin". So, let's take it from here 😉

We will discuss the aspects of Breaks-Glass accounts, password management and do's & don'ts of admin accounts. 

So, buckle up and enjoy the journey.

## Break-glass accounts

A break-glass account is a special account that you can use in case of an emergency, such as when your regular account is locked out, compromised or unavailable. A break-glass account has the minimum permissions required to perform the necessary actions, such as resetting passwords, restoring backups or accessing critical systems. A break-glass account should be used only as a last resort and only for a short period of time. It should also be monitored and audited regularly to detect any misuse or abuse.

To create a break-glass account, you should follow these best practices:
- Use a strong and unique password that is different from your regular account password (also check the next chapter about passwords).
- Store the password securely in a safe place, such as a password manager, a vault or a physical lockbox. Never on the tenant for which the Break-Glass account is intended!
- Limit the number of people who know the password and have access to the account.
- Enable multi-factor authentication (MFA) for the account, if possible.
- Assign the account only the permissions that are absolutely necessary for the emergency scenario.
- Be aware of your emergency scenario, maybe you need more than one break-glass account
- Review and update the account settings and permissions periodically.
- Disable or delete the account when it is no longer needed.

But probably the most important thing is to store the account in a place that has nothing to do with your regular tenant. Use a different password-reset email, and if possible, also use a different mobile number for recovery. 
If the alternative contact options also have something to do with the tenant, you will no longer be able to access them in case of doubt. If you have been locked out of your account, it is useless if the recovery email is sent to an address that is on the tenant. Because you can't get to it.
Try to separate your break-glass account as much as possible from your tenant and also check out [this post for more information.](https://office365itpros.com/2022/01/19/using-break-glass-accounts-microsoft-365-tenants/)

***Craig Says:<br>
The concept of break-glass accounts is rarely heard of, yet an essential need-to-know. Storing of break-glass account details reminds me of films like Armageddon. There’s a hidden suitcase that can only be opened by two people, by turning a key at the same time, just to get the combination. That’s how tight the control needs to be for your break-glass & should be one-time-use. Change the password right away if you have to use one.***

## Good password management
Another topic that every admin should know is good password management. Passwords are one of the most common ways to authenticate users and grant access to resources. However, passwords can also be one of the most vulnerable points of attack, especially if they are weak, reused or stolen. Therefore, you need to follow some best practices to create and manage your passwords securely.

### MFA works: People tend to re-use passwords. We need to avoid that.
Because in the end, it’s usually not weak passwords, that lead to a breach, but human behavior. This is nothing bad, it’s simply a fact that we need to acknowledge when we think about data security. So arguably, it cannot be a good security behavior, if we rely on the weakest part of security (the human) and ask them to keep something in mind, that should be designed to not be kept in mind (complex passwords).<br><br>
Obviously, the answer is MFA. Or using a password manager. Or both. A combination is pretty good, since people would go crazy if they would need MFA for every system again and again. On average we use around 8 accounts during a day that requires a password. That’s why people tend to re-use the same password over and over, and here comes the next problem. If you use the same password for your online poker game as for the sensitive data at your workplace, then we should hope that the online poker game stores the user passwords just as securely as a company that specializes in storing sensitive data. Which is rather unlikely.

![Image that shows the xkcd comic how-hacking-works](/images/how-hacking-works.png)

The problem with the human brain and highly complex machines is this: When you can remember the password, it’s very easy for the computer to “guess” it. And that’s also why “123456”, “password” and “admin” are still used by almost 25% of the accounts (info comes from a [study published bei tech.co](https://tech.co/password-managers/how-many-passwords-average-person)).

Long story short, here is a link to some [recommendations for password manager](https://cybernews.com/best-password-managers/). Use them, and please also tell your friends about them. They store your passwords, and they use complex passwords you could never remember. It’s a win-win.

>***A side note to admins***<br>
Since we know that humans are bad at remembering complex passwords, it would be a terrible, terrible idea to force them to come up with new passwords on a regular basis then, right? I mean, what would you expect in terms of password quality? That's right, it would just get worse and worse.<br><br>
And if you're thinking about the fact that passwords must be changed regularly in your organization, then unfortunately that's because this is a prerequisite for ISO 27001 certification. Yup, the International Organization for Standardisation requires people to come up with new passwords on a regular basis for the organization to be considered secure and to receive an ISO certification. The certification for information security, cybersecurity, and privacy protection.<br><br> 
I’m not a huge fan, but what do I know 🤷‍♂️

### Some passwords recommendations for you ...(and tell your users about it, spread the word)

- Use complex passwords that contain a mix of uppercase and lowercase letters, numbers and symbols.
- Make them long, like 16 characters.
- Avoid using common or predictable passwords, such as your name, birthday, pet's name or keyboard patterns.
- Do not use the same password for multiple accounts or services! Never do that!
- Change your passwords whenever you suspect a breach or compromise (and only then). 
- Use a password manager to generate, store and autofill your passwords securely.
- Enable MFA for your accounts, especially for those that have high privileges or access to sensitive data.
- Do not share your passwords with anyone or write them down on paper or digital notes.
- Beware of phishing emails or websites that may try to trick you into revealing your passwords.

***Craig Says:<br>
Did you know that 59% of adults in the USA use birthdays or names in their passwords? That’s according to these [top password statistics](https://explodingtopics.com/blog/password-stats).<br><br>
In today’s world of social media, a hacker can readily guess simple passwords. Do you post about your birthday, or your wedding anniversary or the name and school of your children? So, not only make different passwords a default action, but make them hard for anyone to guess.***<br>

## Do’s and don’ts for your admin account
If you are new at being an admin or just got thrown into the role of Power Platform admin, let me tell you a few classic mistakes I’ve made through the last year. There are a few things you should be aware of, so let’s dive in 🤿:
1.	Practice good security habits (MFA, PW manager, etc)<br>
What was said earlier in this article about good password behaviour applies all the more to administrator accounts. These accounts have more rights and often access to many, if not all, systems. It is therefore immensely important that they are not compromised. With great power comes great responsibility.

2.	Don’t use it for everyday tasks<br>
Admin accounts are not for everyday use. All "regular" activities, such as checking emails or surfing the internet, are classic gateways for hackers. And it could have catastrophic consequences if a hacker gets into an admin account of all things. Security is always a balance between security and convenience, but believe me: stay safe and use your regular account. Then you'll be able to see straight away if access rights for normal users are not set correctly 😉

3.	Don’t share the account<br>
In the end, you can't trace who did what or what the account was used for. This gets in the way of any audit and only leads to opacity and confusion. And: the more widely a password is used, the weaker it becomes. Unfortunately, I see this practice very often in companies and it is often referred to as "service accounts". You can find out more about service accounts and service principals in Craig and I's next blog. So, short and to the point: The admin account is not a service account and should not be shared (have you ever produced a classic oopsie and afterwards you couldn't tell exactly who was using the account at the time in question? 😇)

4.	Make sure you get admin notifications on your regular account, so you don’t need to be signed in all the time<br>
This is something that happened to me too and I confess: it happened out of convenience. Every time the system sent a message to my admin account, I had to log in again just to read it. In the end, you stay logged in and then there's a big risk that you'll carry out your daily tasks with this account again. This leads to poor audit results and, of course, to an increased risk potential, as already mentioned.
Be cleverer than me and set up a system that gives you an overview of admin notifications. This means you don't have to keep switching and can only use the admin account when you really need it.

***Craig Says:<br>
One of the most prominent things I’ve always lived by for good account health is [PoLP – Principle of Least Privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege). If the admin account(s) you’re using has access to TOO MUCH information, or TOO MANY settings, work to ensure you only have the access you NEED.<br> 
Don’t assume your admin account needs access to everything possible. Microsoft 365 and tools from other vendors will have various administrator roles to apply to accounts. Make sure your admin accounts have the right roles for the tasks.***

## Conclusion
In this blog post, I have outlined three topics that are crucial for every admin to know: break-glass accounts, good password management and general do’s & don’ts.<br> 
These topics will help you enhance your security posture, prevent unauthorized access and reduce the risk of compromise.<br><br> 
If you’re interested further, check out [NIST SP 800-171 Rev. 2 “Protecting Controlled Unclassified Information in Nonfederal Systems and Organizations”](https://csrc.nist.gov/pubs/sp/800/171/r2/upd1/final) and if you want to flex a bit, check out what’s the content of the ISO/IEC 27001 (as it is an official certification, you don't get the content for free. But if your organization is certified, there should be a copy around your legal department, just ask them to see what’s actually inside 😊).<br><br>
We hope you found this post useful and informative and if you want to read more, follow us, we’re going to publish a lot more useful tips and tricks around the admin/governance topic. 
If you have any questions or feedback, please leave a comment below or contact me or Craig directly.
Michael on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)
Craig on [Twitter](https://twitter.com/platformspower) and [LinkedIn](https://www.linkedin.com/in/craig-white-/)

<br> Thank you for reading!

