---
title: 'Let the bots recharge the data volume on your mobile device'
date: Tue, 29 Sep 2020 20:20:55 +0000
draft: false
tags: ['Blog', 'M 365', 'Productivity']
---

I recently build my first Chatbot with Power Virtual Agent and I want to share my experiences with you. At first I wanted to give you an overview over what PVA (that's how the cool kids name it) is and how to get started.

Luckily the amazing [Emma D'arcy, aka TattooedCRMgirl](https://twitter.com/TattooedCRMGirl) got you (and me) covered already. She wrote a pretty complete introduction to Power Virtual Agent and so I decided to not write a similar blog just to repeat what already has been told.

Just check out this very cool blog about it

[Click here](https://tattooedcrmgirl.com/2020/06/18/getting-started-with-power-virtual-agents/)

So, change of plans: I'm just gonna show you a handy little usecase, if you aren't a business owner and want to inform your customers about your opening hours.

The Problem
-----------

In our company we have business mobiles phones and of course there's a specific amount of data volume that comes with it. Since we're quite often working remotely or while traveling (being a consultant can be hard \*sigh) we need to recharge the data volume every now and then.

Usually we had to contact one person from our back-office, explain what we need, give him/her our phone number, and then show some patience.

Funny thing, on almost every request to get the data volume recharge, the back-office needed to know if we've already used our complete data volume. Unfortunately, they can just recharge it, if it's completely done.

And now you might guess how many consultants remembered that little fact:

That's right, almost none of them. So, there was this constant loop, where a consultant complained about being low on data volume, back office explaining that the consultant must use ALL of it, before they can recharge.

The consultant was frustrated, the back-office annoyed, so we lived happily ever after.

Until the bots showed up!

The solution
============

That was just the perfect usecase I was looking for, so I started to build a data volume recharge bot and the best thing?

It took me less than 30 minutes.

Come on, I'll show you how I did it.

Okay, first I wanted to make sure to enter a few trigger phrases, that the bot would be activated. After that I wanted to get rid of that loop, which appeared in every discussion about data volume: I wanted to ask the user to be sure, if all the volume was used.

Fun fact: that eliminated 90% of requests

![](https://gezeitenbrand.de/wp-content/uploads/Pic_1-1-1024x659.png)_How to reduce 90% of all requests with a simple question_

And there comes the first variable. If the user would answer with NO (ehm, what?) I just gave the hint, that it's not possible to recharge the data volume and the conversation would be over. No annoyed back office and an informed consultant.

![](https://gezeitenbrand.de/wp-content/uploads/Pic_2.png)Giving the user helpful tips 💡

If the user answer with yes, on the other hand, the topic progresses further:

![](https://gezeitenbrand.de/wp-content/uploads/Pic_3.png)

The idea is, to identify the user with his e-mail address. That's an easy way to provide an unambiguity. And that step is kind of important for the flow that follows now.

As announced in the bot's message, I added an approval workflow to the user's manager. That way the backoffice doesn't need to do that and wouldn't even be informed if the approval was rejected. After that the user gets a message in Microsoft Teams via an adaptive card. No e-mail, no phone call, all easy and mess-free.

So let's have a look at the flow, shall we?

The Flow
--------

Once again: I wanted to keep things simple, so here you see a minimal version of this (feel free to enhance it and show me your ideas ).

You will need the e-mail address from the chat to identify the manager (given that your AD is up to date ). After that you create an approval, which is assigned to the mail of the manager (I like to identify co-workers with their mail because I know that this field is ALWAYS up to date)

![](https://gezeitenbrand.de/wp-content/uploads/Pic_4.1-1024x767.png)a quick and easy to build flow

![](https://gezeitenbrand.de/wp-content/uploads/Pic_6.png)Hint: Make sure that you check that box "Enable notifications" to YES.

I delivered this approval with an adaptive card, which is a pretty neat feature. The action is called "Post your own adaptive card as the Flow bot to a user" and is sorted to the Microsoft Teams actions. You can just hop over to the [Adaptive Card Designer](https://adaptivecards.io/designer/), assemble the card as you need it and copy that JSON code in the message field on that action. It's that easy.

![](https://gezeitenbrand.de/wp-content/uploads/Pic_8-1024x45.png)_Make sure to select the correct host app and then click "Copy card payload" to get that JSON code_

When you have your Adaptive Card ready, add the action "Wait for an approval" and insert a condition.

Hint: Make sure that you insert the word Approve exactly like that. Capital A and no s at the end. Just type "Approve". It's kind of important. Otherwise it won't work. But please, don't ask me why

![](https://gezeitenbrand.de/wp-content/uploads/Pic_7-1024x464.png)

Depending on the outcomes of the condition, I've once again inserted Adaptive Cards with a simple "Yay" or "Ney" message to inform the user, whether the data volume was recharged or not.

And there you have it. That's all. Now we have A LOT fewer calls and discussions regarding the recharging of data volume. And it just took about 30 min to set this thing up.

I'm going to write a follow up to show you how I published this bot in Microsoft Teams, so that every user could actually use it. There were a few tricks, but that's no sorcery as well.

I would love to hear if you liked it or what you think of it.

Leave me a comment or get me on twitter [(@Gezeitenbrand](https://twitter.com/Gezeitenbrand)).