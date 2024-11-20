---
title: Customize DLP Error Message
description: How to customize the DLP error message, and what you should know about this
date: '2024-12-04T07:11:06.185Z'
images: 
- images/blog/title-customize-error-message.png
author: "Michael Roth"
tags:
  - Power Platform
  - Governance
  - Administration
  - Security
  - PowerShell
type: regular
draft: true
---

Admin's Essentials is back with something that was a thing some time before, but has vanished, at least from my point of view. Again, this mini series is about tasks that an Admin should have done at least once or needs to do re-occuring. Remember customizing the DLP error message in Power Platform? This post is about the why and the how. 

## The Catchy Introduction: The Power of Clear Communication

Ever had a friend who’s great at pointing out problems but terrible at suggesting solutions? That’s what default error messages feel like. They leave makers scratching their heads, wondering what went wrong and where to begin. In Power Platform, we can do better. Let’s explore how to customize error messages that don’t just point to problems—they guide makers toward solutions (well, at least some solution).

![Who doesn't love clear communication?](/images/Error_Message_1.png)

## Why We Should Customize Error Messages

Quite often I would say. default error messages speak the language of the system, not the user. They’re technically accurate but practically unhelpful (like the example above). Yet in Power Platform the message isn't that cryptic.

![Isn't that clear?](/images/Error_Message_2.png)

It tells me that there is a policy violation and even the name of the policy (<span style="color:yellow">yello</span>) 'This is your test' (admittingly not a perfect name for a DLP policy), as well as the connectors. SharePoint is in the business category (<span style="color:green">green</span>), while Azure AD is in the non-business category(<span style="color:purple">purple</span>). 

But I realize that I know this, because I work with this everyday and when it comes to different error messages, I don't read them very carefully. And that's a behaviour I've experienced with lots of people in IT. People don't read. And I can't blame anyone, since I do that myself 😅

So this error message may be clear (to me), yet many get the feeling of being left alone. Yeah, there is a DLP violation, but what does that mean? What can I do now? Is there any kind of information to help me out? Users can feel helpless, even if they read the error message. 

But you know what people like to do? We like to press buttons.  

![Ohhh, it's so shiny, I want to press it](/images/Error_Message_3.png)

Because clicking on a button feels like progress, it will do something. Usually our problems and challenges don't disappear magically, but it feels like there's a way. 

And the customized error messages for DLPs, while being far away from perfect, provides just that: a way to go on.

![An additional textblock with a link and an email address](/images/Error_Message_4.png)

Having a link and an email address makes you feel in control, even when things go wrong.

When a maker runs into an error, it’s a pivotal moment. The right guidance can encourage them to persevere and learn. The wrong one—or worse, no guidance—can discourage them from trying again. By customizing error messages, we can turn mistakes into stepping stones for growth.

## Step-by-Step Guide: How to Customize Error Messages

For this we will need the [Microsoft.PowerApps.Administration.PowerShell module](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.112), which means, we will need at least the **Power Platform Administrator** admin role for this.
If you are new to PowerShell, check out this [Beginner's Guide](https://www.michaelroth42.com/post/2024-04-10-getting-started-with-powershell/), or if you need help with modules, [click on this blog](https://www.michaelroth42.com/post/2024-04-16-ise-modules-and-roles-copy/).

Also I recommend using PowerShell ISE or Visual Studio Code, since we need multiple lines of code (don't panic, there is a template that you can copy-paste).

Here are the variables you need to fill in yourself:

- TenantId = your tenant ID
- url = an URL of your choice, e.g. to a learning SharePoint site collection
- email = an email to an inbox that can help users. First level support would be nice


***Hint***

The easiest way for me to get my tenant ID is to navigate to [make.powerapps.com](https://www.make.powerapps.com), select the **cogwheel** in the upper right corner. Then **Session details** opens a pop-up where you can find your tenant ID.

![How to find your tenant ID](/images/Error_Message_6.png)

Take this code snippet and fill in the variables mentioned above:

~~~
New-PowerAppDlpErrorSettings -TenantId XXXXX -ErrorSettings @{  
  ErrorMessageDetails = @{ 
    enabled = $True  
    url = "TheURLofyourdreams" 
  } 
  ContactDetails= @{  
    enabled = $True 
    email = "An email address" 
  } 
}
~~~

## Another hint

I usually recommend to paste a URL to your own governance documentation, especially the chapter around DLPs. It's important to explain users, what a DLP is, what a DLP error violation means and even guide them to the [Power Platform admin center](aks.ms/ppac), where they can see all DLPs that are active on environments they have access to. 
This way they can see the DLPs, yet not change them. That helps users understand what this error message means.

It just looks like a small additional textblock, but in fact it's a huge difference. Providing guidance and help can make all the difference in the world. Mistakes are a natural part of making, but they don’t have to be roadblocks. With thoughtful error messages, you can transform errors into opportunities for growth, building both confidence and competence in your makers. So, let’s speak their language—and guide them to success.

## Conclusion

I like to talk (write) about customizing the DLP error message, because it's such a simple and tiny task, yet it can make a huge impact. A customized dlp error message clearly shows the difference that a well thought-out governance concept can have on users: Governance isn't about shutting doors; it's about building pathways that empower users to innovate safely and confidently within a well-defined framework.

---

If you've heard me talking about Power Platform Governance 101 on an event, watch out for more posts tagged with "Admin's Essentials", that's where I explain all the important things that you need to be aware of ⚠️

Thanks a lot for reading, and if you have comments, questions, or remarks, feel free to contact me on social media. I'm happy to chat and help and learn 😉

Michael on [Bluesky](https://bsky.app/profile/michael42.bsky.social) and [LinkedIn](https://www.linkedin.com/in/michaelroth42/)

<br> Thank you for reading!