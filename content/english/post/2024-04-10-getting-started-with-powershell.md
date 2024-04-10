---
title: Getting started with PowerShell - A Beginner's Guide
description: A beginners guide to PowerShell, specifically for Power Platform Administrators
date: '2024-04-10T07:11:06.185Z'
images: 
- images/blog/title-getting-started-with-powershell.png
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
  - PowerShell
type: regular
draft: false
---

Hello dear Admin friends and welcome back to ppacAttack with Craig and me. In today’s blog I finally dare to touch a topic that I’m in a love-hate-relationship with. 

The almighty PowerShell.

Why is it a love-hate-relationship you wonder? I’m glad you asked. On the one hand, it’s a powerful tool that unlocks a whole new level of possibilities, especially when we think about administering Power Platform. It’s fast, it’s reliable plus it looks super cool when you sit in front of a terminal release some automation magic with only a CLI 😎

On the other hand, it’s rather frightening for me. I know how much I can f*ck things up, when I’m not careful, I never officially learned how to use it and complex PowerShell scripts still feel like magic to me. 

But we rise by facing our fears, right? So buckle up, because we’re going to guide you through a beginners course on how to use PowerShell for administering Power Platform. If you’re up to it, we even have a few challenges and all. It’s gonna be great.

 
![Craig says header](/images/CraigSays.png)
*Hahaha, I’m the same here. PowerShell has always been a bit of a dark art for me, too. It’s not of course, and I’ve worked with many a talented person who’d do everything in PowerShell, but I’ve never really vibed with it. So, I’m delighted we’re tackling this subject, as I’ll be learning along with everyone reading*

## What Is PowerShell?

PowerShell is an open-source, command-line interface (CLI) based tool that allows developers, IT admins, and DevOps professionals to automate tasks and configurations using code. Here are some key points about PowerShell:

1.	CLI-Based Tool:
>- CLI stands for Command-Line Interface. It’s a way to interact with a computer system using text-based commands.
>-	In PowerShell, you type commands in the console, and it executes them. Think of it as a powerful text-based control center for your computer. We call those commands cmdlets (pronounced command-lets). 

2.	Bifunctional Attribute:
>-	PowerShell serves two main purposes: 
>>- Shell: As a shell, it lets you control the computer using commands from the command line. You can automate repetitive tasks, reducing errors and making work easier.
>>- Scripting Language: PowerShell is also a programming language used to pass instructions from one software to another. Unlike compiled languages, PowerShell commands are interpreted line by line.

3.	Origins and Evolution:
- Created by Jeffery Snover, PowerShell was initially known as Monad *(free weird knowledge for your next pub-quiz🤓)*.
- It was designed to work as an extensible CLI with fresh designs that could host Unix tools.
- Over time, it evolved into Windows PowerShell, and by 2016, version 5.1 was launched.
Now PowerShell is pre-installed on all modern Windows operating computers. We just have to check which version is installed on your system, since I will be talking about PowerShell 5.1.

## Start PowerShell

To start Powershell, select the Windows Start Button and type “Powershell” into the searchbar. You should see at least two different applications with the name “PowerShell”. Windows PowerShell and Windows PowerShell ISE (I will explain this in part 2 of this mini-series).

![How to start PowerShell](/images/PowerShell_1.png)

When you click on Windows PowerShell a blue CLI should open, that may look a bit like this (my versions uses a fancy [oh-my-posh](https://ohmyposh.dev/) theme, which is used to make any shell a bit more pretty). 

And that may already be everything, but we have to consider that we sometimes need to run PowerShell as administrator, especially when we want to administer things, like Power Platform. The documentation says that PowerShell doesn’t participate in User Access Control (UAC), which means it won’t run cmdlets that require an admin role. Which is a good thing, so we don’t accidentally run things we shouldn’t run. But then again, sometimes we need to do exactly that and then we can run PowerShell as an administrator. 

For that we once again, select the Windows Start button, type Powershell in the search bar, but this time we right click Windows PowerShell or use the option on the right-hand side Run as Administrator.

![How to run PowerShell as administrator](/images/PowerShell_2.png)

You can even quick check if your shell is running in regular or administrator mode by looking at the window. The administrator version as a little shield to indicate its power and might. 

![Check if PowerShell runs in administrator mode](/images/PowerShell_3.png)

Now before we go on, let’s quickly check your current version of PowerShell. Therefore lets use the variable 

`$PSVersionTable`

(Whenever I will display code snippets, I will just display the code, so you can copy paste it directly into your terminal, if you like)

This is the result and in the line PSVersion I can see that my version is 5.1 which is just fine 😊

![result of the PSVersionTable cmdlet](/images/PowerShell_4.png)

## A few tips right at the beginning
Before we end this first introduction, here are a few tips that will make your like in the shell definitely easier.
1.	When you press the up arrow in PowerShell it will show you the last command that you’ve typed. Using this you can cycle through your latest commands, which can be not only a timesaver, but also prevents typos AND frustration 😉

2.	When pressing the Tab key you can cycle through commands that start with the letters you already typed. That means, if you can’t remember exactly what the cmdlet was called, type the first few characters and press Tab until you find what you are looking for (works also, if you are too lazy to type 😇 – pro tip, they are shown in alphabetical order).

3.	PowerShell commands follow a pattern and if you grew up with late 80s and early 90s adventure games like Monkey Island or Maniac Mansion, they might feel familiar. 

PowerShell commands consists of two words separated by a hyphen. A verb and an object. Get-AdminFlow or Remove-AdminFlowApprovals or WalkTo-Archway (okay, okay, the last one may be from Monkey Island)

![An image from Monkey Island? What?](/images/PowerShell_Monkey.png)

![Craig says header](/images/CraigSays.png)
*OMG I loved Monkey Island! Sorry, continue...*

But seriously, a short example from the command list makes clear what I mean:

![A list of cmdlets from the PowerPlatform module for PowerShell](/images/PowerShell_5.png)

4.	The admin calls for help! And the shell will answer. Because the help system is pretty clever and you should use it all the time. At least that’s what I do. There are two super important cmdlets that you need to know:

>>>>a.	Get-Help
>>>>b.	Get-Command
(see the verb-noun combination? Just like in your favourite text adventure 🤓)

**Get-Help** is used to get more information about specific cmdlets and it shows you how to use them. If you use the command Get-Help enable-AdminFlow you will get the help text for that command:

![A list of cmdlets from the PowerPlatform module for PowerShell](/images/PowerShell_6.png)

At the top we have our get-help cmdlet and I often use that to see how a command is used, i.e. the syntax, then I get a description as well as further remarks how to get even more help.
There is a lot more to learn about the Get-Help cmdlet, so maybe use [this link to the official documentation](https://learn.microsoft.com/en-us/powershell/scripting/learn/ps101/02-help-system?view=powershell-7.4#get-help).

**Get-Command** is great for when you want to get an idea which commands there even are. When you run Get-Command without any parameters you will get a list of all the commands that are on your system (and usually that’s a long list) but you can run the command with a bit more information. For example:

Get-Command -Noun Process 

This cmdlet will show you a list of all commands with the word “process” in it. The result may look like this: 

![A list of all cmdlets with the word process](/images/PowerShell_6.png)

So, if you are a Power Platform Administrator, maybe you want to see a list of all the commands that have something to do with environments. If we’d try Get-Command -Noun Environment that would return nothing, because there is no command that only has the word environment in it, but we can use wildcards here, which is really helpful. Try this one instead:

Get-Command -Noun *Environment 

![A list of all cmdlets with the word environment](/images/PowerShell_7.png)

The results look better and lists us every cmdlet that contains some text before the word “environment”. 

As a follow up we can use the Get-Help cmdlet to get more information on these commands 🤓

And of course, there is more to learn on that as well, but that’s how I use the help system. [Here is the link to the official documentation](https://learn.microsoft.com/en-us/powershell/scripting/learn/ps101/02-help-system?view=powershell-7.4#get-command) if you want to learn more. 

## Conclusion

We’ve learned what PowerShell is, how to start it, how to check the current version and a few first cmdlets as well as some tipps and tricks. If you are interested to finally do something useful for Power Platform, follow me to the second part, where we install some cool Power Platform modules from the PowerShell Gallery and start to write our first command that may actually be useful for our everyday work 😊.

![Craig says header](/images/CraigSays.png)
*For most graduating to the Power Platform admin role, you’ll likely be the person in the business who’s built some apps and knows the most about the services. Your default for getting some information might be Power Automate, as this is easier to configure for someone with less programming experience. But sometimes, there’s settings across the Power Platform (and other areas of the Microsoft stack) that can only be configured via PowerShell. So this is a good tool to begin to understand – even if only theoretically to begin with, so you have the knowledge to pull out when you need to.*


As usual, thanks for reading, if you have questions, comments, and stories to share, find us on social media and let’s talk. We can all learn from each other 😊

Michael on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)
Craig on [Twitter](https://twitter.com/platformspower) and [LinkedIn](https://www.linkedin.com/in/craig-white-/)

<br> Thank you for reading!




