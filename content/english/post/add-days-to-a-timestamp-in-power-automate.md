---
title: 'Add days to a timestamp in Power Automate'
date: Mon, 21 Dec 2020 08:08:07 +0000
draft: false
tags: ["Blog","M 365","Nugget","Planner","Power Automate"]
---

Learning Nugget: Power Automate
-------------------------------

Add days to a timestamp in Power Automate in order to create an automated flow and remind you of your community tasks 💡

Right now I’m in between jobs and most of you know, that I’m a huge fan of [Microsoft Planner](https://www.microsoft.com/en/microsoft-365/business/task-management-software), [To Do](https://www.microsoft.com/en-us/microsoft-365/microsoft-to-do-list-app) and [Power Automate.](https://www.microsoft.com/en-us/microsoft-365/business/microsoft-powerapps) As far as my tasklist and my (work) commitments are concerned, I have to wonderful possibility to start from scratch. Leave all those different lists and plan behind you and do it right from the start.

[Luise Freeses post about overcommitting](https://m365princess.com/how-to-avoid-overcommitting/) spoke to me and so I got inspired to do set up a Microsoft Planner board with all my (community) commitments. To visualize what I am doing, to not loose focus, to get a clear vision of what I want to do and not drown in ideas and projects.

Another thing that was super helpful for me was writing down these [Learning Nuggets](https://gezeitenbrand.de/learning-nugget-displaying-imagines-in-a-gallery-in-powerapps/). Teeny tiny learning steps. I see it as a learning diary for myself.

I wanted a flow in Power Automate that would add another task on my commitment plan and remind me in To Do, whenever I finish a task:

*   I want to acknowledge that I just finished that task. I want to celebrate even the small steps.
*   I want to write down, what I’ve just learned and publish that, whether in a blogpost or a Learning Nugget.

So I needed this flow

![](https://gezeitenbrand.de/wp-content/uploads/Flow_short.png)

And do you know what I always forget? How to edit timestamps in Power Automate expressions 😅  
So here it is:

```
formatDateTime(addDays(utcNow(),2),'dd-MMMM-yyyy')
```

My Flow reminds me, two days after I finished a project that I want to acknowledge it AND write down what I’ve learned. Jesus, I would forget my head, if I hadn’t written a flow for that 😂

And that's how you add days to a timestamp in Power Automate in order to create an automated flow and remind you of your community tasks.