---
layout: page   # This is required
title: Useful External Github Services   # This is required

order: 70    # Determines the order of units. Doesn't need to be consecutive though
            # or even start with zero, the pages will be displayed in their sort
            # order.

duration: 5 # A hint to how long it will take to cover this topic in mintues.

tutorial: true  # Set to true if you want this page displayed as a web page
instructors_notes: true  # Set to true if you want this displayed in instructors notes

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  There are many applications, websites and services that use Git and GitHub in some way.
  The examples given here are included just to give a little taste of the sorts of things
  that exist.

instructors_note: |
  


---

External services can open themselves to Git and GitHub in two ways. First, they can just 
use remote repositories to allow you to create a repository on their platform. 
Secondly, many services avail themselves of GitHubs APIs to integrate themselves more 
deeply into GitHub. The services outlined below are just some of the many potentially 
useful services you might find. It does pay off to spend a little time researching if 
there is a particular need you have. We have already touched on one popular service, 
[ZenHub](https://www.zenhub.com/), here are a few more. 


## Figshare

[Figshare](https://figshare.com/) is a popular commerical repository used by many researchers to archive 
and share their work. It has a pretty easy integration into GitHub. Just go to your **application** settings (after you have an 
account), and connect to GitHub. Then on the **My data** tab click on the GitHub icon to import the repository of choice. See the 
[full documentation](https://knowledge.figshare.com/articles/item/how-to-connect-figshare-with-your-github-account-1) for more detail.

## Open Science Framework

[The Open Science Framework](https://osf.io/)(OSF) is an open source and free service for managing, archiving and sharing your work. 
You can connect it to a variety of services including GitHub. Others include Box, DropBox, and Amazon S3. 

## Amazon Web Services

[Amazon Web Services](https://aws.amazon.com/)(AWS) provides an array of services. Some of these integrate GitHub via remote. Others
integrate more closely using their APIs. If you are working on larger and collaborative projects, AWS may be a useful tool. Some of the
services that work well with GitHub are Cloud9, Code Pipeline and Code Deploy.

## Travis CI

[Travis CI]() is a popular tool among software developers and included here as an example of the many services that might be useful
for more software intensive projects. It is an **Continuous Integration** service that takes automated tests written for software 
and runs them whenever certain types of activity are detected in a GitHub repository. It is a great way to ensure your code 
is always functioning. It is often used with pull requests, only permitting them to be merged if the continuous integration tests 
pass.










