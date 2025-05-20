---
title: Rubber Ducks and Emotional Damage
description: A practical guide to troubleshooting Power Platform issues by managing error messages, logs—and your own emotional meltdown. 
date: '2025-05-19T07:11:06.185Z'
images: 
- images/blog/title-RubberDucks.png
author: "Michael Roth"
tags:
  - Tech
  - PowerPlatform
  - Administration
  - Troubleshooting
  - Debugging
  - Microsoft
type: regular
draft: false
---

# 🦆 Rubber Ducks and Emotional Damage

**Troubleshooting Power Platform with logs, tears, and the occasional Starfleet duck.**

Everything’s broken. Again.

No error code, or worse—an error message so vague it might as well just say *“Good luck, loser.”*

You feel it bubbling up: frustration, self-doubt, the need to loudly declare that “this worked yesterday!”—as if the system might feel guilty and fix itself.

I’ve been there. Too often, actually.

When I started working in tech, I thought troubleshooting was about knowing things—knowing the system, the logic, the right buttons to click. But I’ve since learned:

> **Troubleshooting is mostly about how you behave when you don’t know.**

It’s about staying calm when your brain is screaming.  
It’s about reading error messages instead of rage-quitting.  
It’s about resisting the urge to push blame onto the tool, the platform, or the nearest coworker.

And most of all, it’s about shifting your state of mind—from emotional storm to analytical story mode.

That shift is what makes all the difference.  
Everything else—logs, tools, documentation, even the wise gaze of Geordi La Quack—is just support.

That realization is also why I started this blog in the first place.  
Because half the time I solve something, I immediately forget what I did.  
And the next time it breaks? I feel just as lost—until I find an old post of mine and think:  
*“Oh right. I do know this. I’ve just… been here before.”*

This blog post is my attempt to capture that moment.  
The one where frustration turns into clarity—and chaos becomes a story you can actually tell.

It’s not a checklist.  
It’s not a magic fix.  
It’s a messy, very human process that I've slowly learned (and keep re-learning).

If someone else finds it helpful too, even better.

---

## 🧠 Chapter 2: The Core of Troubleshooting

Here’s the thing no one tells you when you start in tech:

> **Troubleshooting isn’t really about tools. It’s about how you deal with being stuck.**

When I was younger, getting stuck felt like failure.  
I’d get frustrated. I’d feel dumb. I’d blame the system, the update, the user, the computer—anything to not feel like it was me.

And in that state? I wasn’t thinking clearly.  
I wasn’t investigating. I was defending myself against my own insecurity.

But over time, I learned to recognize the shift.  
The moment where I go from:

> “Why doesn’t this work?!”  
> *to*  
> “Okay. What’s actually happening here?”

That shift—from emotional storm to analytical story mode—is the core of troubleshooting.

Let’s talk about it. The panic. The blame. The voice in your head that says:
- *“I should already know this.”*
- *“What if I break it even more?”*
- *“Why does this always happen to me?”*

These reactions don’t mean you’re bad at your job.  
They mean you’re human.  
But if you stay in that storm, you can’t see clearly.

> **Strong emotions prevent rational inspection.  
> Frustration builds walls. Curiosity opens doors.**

💡 **Let the emotion pass before investigating.**  
If you're too upset to think clearly, you're not troubleshooting—you're protecting your ego. Pause, breathe, then return with curiosity.

When you calm down—when you stop taking the error personally—you start to see the issue like a puzzle.

You become an investigator, not a victim.  
And the weird thing is—it actually feels good. Even fun, sometimes.

### 💡 Julia Evans calls this out beautifully in her [Debugging Manifesto](https://jvns.ca/blog/2022/12/08/a-debugging-manifesto/):
- *Being stuck is temporary.*
- *There’s always a reason.*
- *It can be an adventure.*
- *It’s probably your code.*
- *Trust nobody and nothing.*

That last one isn’t cynical. It’s about letting go of assumptions.  
Just because you think something should behave a certain way doesn’t mean it does.  
And honestly? That mindset shift helps a lot when you're dealing with low-code platforms where "magic" often hides actual logic.

### 🧠 My personal core principles:
- 💡 **There is always a reason, even when it feels random.**  
- 💡 **Strong feelings block clear thinking.**  
- 💡 **Calm is a tool.**  
- 💡 **You’re not dumb. You’re just not done.**

![Michaels pro tipp](/images/ProTipp.png)
---

## 🧰 Chapter 3: Methods and Tools That Help  
*(Once You’re Calm Enough to Use Them)*

So you’ve made the shift. You’re out of panic mode. You’ve stopped yelling at your screen (or at least reduced it to grumbling). Now it’s time to actually investigate.

This is where the tools come in.  
Not just fancy admin tools—also the mental ones.  
The habits, questions, and tiny decisions that help you make sense of chaos.

💡 **Narrow things down.**  
Is it only happening in one environment? Is it tied to one account?  
I try to reproduce the error *and* eliminate everything that probably has nothing to do with it.

If I can make it break differently, I know I’m getting closer.

> Producing a new error message might not look like progress from the outside—but to me, it’s gold.

💡 **Read the actual error message.**  
I used to skip them, thanks to years of vague garbage like *"Something went wrong."*  
But these days, I always read them. I Google the weird stuff. I ask colleagues.  
Sometimes the one-liner at the bottom is the key.

💡 **Use the logs—but format them first.**  
I once opened a massive XML log file in VS Code and got absolutely nothing from it. Just noise.  
Then I opened it in Excel, and there it was—perfectly formatted with the problem staring me in the face.

> **Bad formatting hides good information.**

💡 **Explain it out loud.**  
Rubberducking is real.  
I talk through what I’ve seen, what I’ve tried, and what I think is going on.  
Somewhere in that monologue, a pattern usually shows up.

Bonus points if your duck wears a Starfleet uniform.

💡 **Try one thing at a time.**  
We all know this, but it’s hard to do when you're desperate.  
Still, it matters.  
If you change three things and it works, you won’t know which one mattered.

💡 **Write it down. Seriously.**  
If you don’t, you’ll try the same thing five times and wonder why nothing's changing.

Honestly, that's one of the main reasons I started this blog—  
to remember what I actually know, before I forget I ever figured it out.

These tools won’t fix the issue for you.  
But they *will* keep you sane and help you stay on the trail.

---

### 🛠️ Quick Recap: My Go-To Troubleshooting Tools

- 💡 Narrow the scope (user, environment, input)  
- 💡 Reproduce *and* simplify  
- 💡 Read error messages (yes, even the weird ones)  
- 💡 Format logs properly (try Excel!)  
- 💡 Explain it out loud (rubber ducks encouraged)  
- 💡 Change one thing at a time  
- 💡 Document what you try

![Michaels pro tipp](/images/ProTipp.png)

---

## 💡 Chapter 4: Helpful Tipps and Tricks  
*(aka “the weird little things that actually work”)*

Not everything about troubleshooting is deep mindset work or tool mastery.  
Sometimes, it’s just the little things.

💡 **Take a break.**  
No seriously. Walk away. Drink water. Talk to a human.  
If you’ve been staring at the same bug for an hour, you’re not debugging—you’re just baking frustration into your brain.

> **Debugging while angry is like doing surgery in a hurricane.**

💡 **Screenshot everything.**  
The error, the test run, the log line.  
Half the time I fix something, the error disappears.  
And then nobody believes it ever happened.

💡 **Reboot the world.**  
Clear your cache. Use another browser. Go incognito.  
These feel like cheap tricks—until they work.  
And then you’re a wizard.

💡 **Clone it. Strip it down. Rebuild it.**  
Sometimes breaking things into smaller pieces is the only way to see where it cracks.

💡 **Talk to someone.**  
Post it on a forum. Ping a friend. Say it out loud to your cat. Doesn’t matter.  
Just don’t do it alone.

💡 **Don’t trust your assumptions.**  
They should work. But they don’t. Not always.  
So test everything. Especially the stuff you’re *sure* about.

💡 **Build your own toolkit.**  
Save good logs. Bookmark weird bugs.  
Capture solutions somewhere you can find them later.  
Future you will be grateful.

These aren’t “best practices.”  
They’re just things that help.

Mix them with the mindset shift, the structured approach, and your personal debugging rituals—  
and you might just start to enjoy troubleshooting.

---

## 🧵 Outro: Your Turn

If you made it this far: congrats.  
You just debugged my brain.

This post started as a list of tools, and turned into an emotional unpacking of frustration, ego, and rubber ducks in Starfleet uniforms.

And maybe that’s the point.  
Troubleshooting isn’t just fixing stuff.  
It’s about staying with the problem long enough to turn noise into clarity.

Now it’s your turn:

- What’s your go-to troubleshooting move?  
- What mindset shift saved you?  
- What’s the weirdest bug you’ve ever fixed (or given up on)?

Find me on [LinkedIn](https://www.linkedin.com/in/michaelroth42/) an [BlueSky](https://bsky.app/profile/michael42.bsky.social) and let’s make troubleshooting just a little more human.
