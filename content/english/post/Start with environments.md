# Start working with environments in Power Platform

Working with environments in Power Platform is a major keystone of governance and security. I am always surprised how rarely they are really used though. Here is a blog about the fundamentals of environments to help you get started.

## What?

Environments are containers that contain your data, apps and everything else that you need to work with Power Platform. These containers have boundaries to differentiate them from other environments, including permissions and security settings.
This way you can build layers that will help you and your user building secure apps and workflows. Each layer serves its own purpose.

## Why (should you care)?

There are multiple good reasons to start working with environments. If your business is operating in different countries with different data security requirements, you can separate the data with environments and secure them each according to the regulations.
Or you can create development and testing environments which allow you to develop and test apps without harming your productive environment and give you more control over the Application Lifecycle Management.

## How does it work?

### What kind of environments are there?

Before I give you a brief overview, here is how you can check what environment you're in and what others environments you have access to. When you're on [flow.microsoft.com](www.flow.powerapps.com) or [make.powerapps.com](www.make.powerapps.com) you will see your current environment in the upper right corner.

{{< image src="images/blog/Environment1.png" >}}
Right now I am in an environment that is called "CoE Demo".

If you click on that environment you see a list of all environments you have access to. Maybe you see but one environment that is called "[(default)" in the end. That is your default environment, which everyone has access to per default. Every time a new user gets added,  that user gets added to this default environment as well. 

{{< image src="images/blog/Environment2.png" >}}

Let's first start with a quick overview over what kind of environments there are, before I walk you through the basic steps of creating a new environment and adding user to them.

### Default Environment

Every organization has a default environment and there is a database connected to that environment. All of your users start creating apps and flows in this environment, which is the reason why most organization use that for personal productivity.

Security: Every user has the security role "Environment Maker" in the default environment. That means they can create new apps, flows or connections. **That role doesn't grant access to data though**. I will list all security roles and what you may need later in this article.

### Production Environment

These environments are used for long term working scenarios that don't require special features. Microsoft recommends these for the most usecases: *"Production environments are what you should use for any environments on which you depend."*
You can convert your production environment into a sandbox environment anytime. Of course you can convert it back into production as well.

{{< image src="images/blog/Environment2_convertToSandbox.png" >}}

### Sandbox

Sandbox environments are similar to production environments but you have the possibility to copy, reset it and convert it into a production environment as well (**if your sandbox environment has a database, if it doesn't you don't get those options*).
If you **copy** your environment, you're basically overwriting another already existing environment. Now you can choose if you want to override everything or just customizations and schemas.

{{< image src="images/blog/Environment2_copy.png" >}}

If you **reset** your environment you set it back to factory settings, deleting everything, including the backups.

{{< image src="images/blog/Environment2_reset.png" >}}

Trial
Trial (subscription-based)


With or without database?
*to future Michael: you're welcome*
Requirements to create new environments
Create a new environment
Add a security group
add user

Example case for dev, test and prod environments?
