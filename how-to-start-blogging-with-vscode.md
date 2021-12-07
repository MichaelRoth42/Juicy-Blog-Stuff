# How to start blogging with VScode

## What?

I'm trying to get more comfortable in VScode, since I realize that it helps me develop a better understanding of tech. Many of you might know already, I don't have a tech background, so sometimes I struggle with things. But the more I familiarize myself with, let's say Github and VScode, the better I understand how things work together.

Therefore I started to write my blog posts with VScode and **not** with MS Word anymore. From VScode I commit them to github, using my terminal.

It's not easy for me to get behind all this, but here is my short explanation of the why and the how, if you'd like to start with it as well 😊

## Why (should you care)?

I used to write my blogs with a text editor, e.g. Microsoft word. It's obvious, isn't it? Use the right tool for the right job (use a text editor for writing texts). But there are a few benefits from using VScode and Github for blogging:

1. I get a better understanding of how **Github** works. Open Source is an amazing idea and I would love to contribute more. Therefore it's actually helpful to get better with Github. I created a repository in Github that contains all my texts and imagines that I need for my blog.

2. I familiarize myself with working in **VScode**. I use the terminal on a regular basis (my approach works with the UI too). Working with a console and VScode loses a bit of complexity and thus its horror 🙂

3. Since I blog for and with the tech community, I want to share my insights. This way I have very **good control** over what is still locally on my computer, and what's already shared with the community. I can even check afterwards what exactly I did at any given time.

4. I **don't need to copy/paste** my blogs from Word into a different tool (I know there are other options to reach this goal but hey...), which saves me a lot of time.

5. I get better at writing **markdown** 🤓

6. I have a very **clear structure of my texts and images**. I'm not very good at keeping things tidy, but Github gives me a good structure. It just works pretty good for me.

## How does it work?

It's actually not as complex as I thought it was. It's three steps:

(0. Create a repository on Github to store your blog posts and images.)

1. Create a local copy of your github repository

2. work on VScode locally (in my case I write my blog)

3. push/commit(?) your created content on Github

Now, let me guide you through each step for you to try it out for yourself.

### Create a repository on Github to store your blog posts and images

### Create a local copy of your github repository

Actually that is something you need to do only the very first time, when you decide to try this approach. After you created a local copy, it's just there (maybe you need to update it, but more about that later).
To do this, you navigate to your Github repository and select "Code" and select the copy button to copy the URL of your repository.

![a picture how to copy the url of your Github repository](clone-repository-locally.png)

Create a folder locally. You will work in this folder and push that content to Github later on.

Then open the code editor of your choice (I use VScode) and open the folder you just created.

![a picture showing how to open folders in VScode](open-folder-in-vscode.png)

Now open the terminal to create the local copy of your Github repository (make sure that your terminal is in the local folder you just created). To clone the repository you will need your first powershell cmdlet:
type `git clone [url of your repository you copied earlier]` (without the square brackets).

Congratulations, you just created a local copy of your Github repository. You should see it in the left panel of VScode.
![a picture showing the local copy of my Github repository in VScode](local-copy-repo.png)

### work on VScode locally

Now you can create a new file in your repository (I use the UI element on the left hand side). Make sure to let it end in .md to tell VScode (and Github) that this is a markdown file.

![a picture showing how to add a new file in VScode](create-new-file.png)

Then you can start writing your text (there are a few extensions that I use, to make it easier, like the Docs Authoring Pack, Grammarly or the Code Spell Cheker. Maybe I cover that in a different post or see to link a good resource for you).

### push/commit(?) your created content on Github
