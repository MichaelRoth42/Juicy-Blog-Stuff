---
title: From managed to unmanaged
description: "This blog describes how to import a managed solution as an un-managed in case you accidentally deleted your backup"
date: '2022-09-16T08:11:06.185Z'
images: 
- images/blog/title-managed-to-unmanaged.png
author: Michael Roth
tags: 
    - Power Platform
    - Governance
    - Administration
    - Security
    - Solutions
type: regular
draft: false
---

## Oops, I accidentally deleted the backup

No, I never wanted to hear that sentence again. Yes, I did anyway.

The question is, how you can change your managed Power Platform solution into an un-managed one? Let's have a look at the scenario first:

You develop Power Platform solutions in a development environment, then you export them as a managed solution into your UAT/test environment, so users can test it, but not change it anymore!

![Image that shows a flowchart how to export a solution as managed from the developer environment and as managed to an UAT/testing environment](/images/ManagedAsUnmanaged_1.png)

Now what happens if, by any means, somebody would accidentally delete the un-managed solution on the development environment? <br>You can't export the managed solution from the UAT/testing environment anymore.<br>
If you still have the zip file, you can only import it as a managed solution.<br>

![Image that shows a flowchart with a missing solution in the developer environment, leaving only the managed solution in the UAT/testing environment](/images/ManagedAsUnmanaged_2.png)

Or can you?

## The Solution

In the zip file of your managed solution is a solution.xml file that has a tag called Managed with the value of 1 in it. That indicates that your solution is managed and will stay managed.

![Image showing the content of the solution.xml file within in the zip folder of the managed solution, indicating to the Managed-tag](/images/ManagedAsUnmanaged_3.png)

If you unpack it, edit the value to 0 (zero), save it, pack it again and import it, you will notice two things:

1. It is recognized as un-managed, which is good
2. you get an error message saying the zip file is invalid, which is bad

![Image showing error message when we try to import our edited solution](/images/ManagedAsUnmanaged_4.png)

The trick is, that you must not unpack the zip folder, while editing the content. You have two possibilities for that:

1. Open the zip folder, cut the solution.xml file with CTRL+X and paste it somewhere, where you can edit it. Then cut it with CTRL+X again and paste it into the opened zip folder again
2. Use 7.zip as it allows you to open a zip archive and edit the files in the archive without actually unpacking the file. Open the file with 7zip, right click on the solution.xml file and select edit. You can now edit the file and save it again. Click **OK** when 7zip asks you if you want to update the archive

![Image how to edit the content of a zip file with 7zip without unpacking it](/images/ManagedAsUnmanaged_5.png)
![Image showing the message when updating a file within an archive](/images/ManagedAsUnmanaged_6.png)

The import works without any issues and here we have our solution. Notice how it's now un-managed and allows us to edit the content just as we please.

![Image showing the solution marked as un-managed in our environment](/images/ManagedAsUnmanaged_7.png)
![Image showing a flowchart that shows that the managed solution was imported as un-managed again](/images/ManagedAsUnmanaged_8.png)

[I welcome comments, remarks and discussions](https://twitter.com/MichaelRoth42/status/1564508722508009472?s=20&t=2qvzxiSj03RvPNT6OqpnWw) about your experiences with Power Platform Governance.

Find me on [Twitter](https://twitter.com/MichaelRoth42) and [LinkedIn](https://www.linkedin.com/in/michael-roth-handsomeguy/)

---

[Photo in header image by Bucography](https://unsplash.com/photos/LwWPNOCiK-g)