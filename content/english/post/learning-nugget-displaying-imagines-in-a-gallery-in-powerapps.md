---
title: 'Learning Nugget: Displaying imagines in a gallery in PowerApps'
date: Thu, 26 Nov 2020 08:56:32 +0000
draft: false
tags: ['Blog', 'M 365', 'M365', 'Microsoft 365', 'Nugget', 'Nugget', 'PowerApps', 'PowerApps', 'SharePoint', 'SharePoint']
---

**_Disclaimer Learning Nuggets_**  
_These nuggets are mini learnings that happened to me. Quite often I have the feeling that the things I'm learning a no-brainer for others but here are my thoughts about it:_

1.  _If I struggled with something, there will be others who will run into the same challenge_
2.  _Even if not, this is an awesome learning diary for myself_

* * *

I wanted to display images in a gallery in PowerApps, easy, right?

Every time you add a gallery there are a lot of default layouts that let you display images. This problem may seem to be a no-brainer, yet I needed some time to find the solution and even Dr.google didn't help at first.

But it didn’t work for me right away, so here’s the context of my problem. I have a SharePoint list with a Thumbnail column which contains a picture (I added an image column, in the list settings SharePoint displays that list as a thumbnail column however).

![](https://gezeitenbrand.de/wp-content/uploads/SharePoint-List.png)

_Figure 1 The column "pic" doesn't show up in PowerApps at all_

Unfortunately PowerApps can’t display these thumbnails. I couldn’t even reference to that column at all. It just didn’t show up.

So I added a Hyperlink or Picture Column to solve that. You can choose to format the URL as picture or hyperlink.

![](https://gezeitenbrand.de/wp-content/uploads/Hyp_Pic.png)

Both works fine in PowerApps. The thing is, you can’t just upload a picture, but have to provide a URL.

![](https://gezeitenbrand.de/wp-content/uploads/Use_URL.png)

Easiest thing for me was to create another SharePoint library, upload all the pics I needed and get the URL from there to paste them into my SharePoint list.

Back in PowerApps you can select your Gallery. Click on the sample image and set the property Image = ThisItem._NameOfYourColumn_

My Hyperlink or Picture Column is named Pic\_2 (I know, that’s not very clever 🙈) so the property in my app is...

Image = ThisItem.Pic\_2

![](https://gezeitenbrand.de/wp-content/uploads/Image_Function.png)

Et voilá – there you have it 🤓
---
### Comments:
#### 
[Add days to a timestamp in Power Automate - Gezeitenbrand](https://gezeitenbrand.de/add-days-to-a-timestamp-in-power-automate/ "") - <time datetime="2020-12-21 09:11:19">Dec 1, 2020</time>

\[…\] thing that was super helpful for me was writing down these Learning Nuggets. Teeny tiny learning steps. I see it as a learning diary for \[…\]
<hr />
