---
layout: page
title: Getting Started With GitHub

order: 27

duration: 20

tutorial: true  # Set to true if you want this page displayed as a web page
instructors_notes: true  # Set to true if you want this displayed in instructors notes

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  Git becomes an incredibly powerful collaboration and publishing tool when coupled with GitHub.
  While it may seem confusing at first, GitHub is really just another Git repository. Git has
  the ability to communicate with any other repository built right in. GitHub just provides a web 
  interface and many other services to help manage and publish our projects.
  
  At this point we refer to the Git repository on our local computer as a *_local_* repository. Other copies 
  of our work on other computers are called *_remote_* repositories. By convention, we 
  work with our collabortors by coordinating through a single remote repository, in this case GitHub. 
  
  In this unit we create a copy of our local repository to GitHub by **pushing** it. We edit it
  using the GitHub interface, then **pull** it back into our local repository.
  
  
instructors_note: |
  1. Create a GitHub repo
  2. LInk with an existing repository
  3. Clone a repositry
  

  
# These should resolve to files in the supporting_files directory
# or if you specified a different one in _config.yml use that.
# The link_text can be anything you want.
# supporting_files:
#   - file:
#     file_name: first_example_file.txt
#     link_text: Example file  for this unit.
#   - file:
#     file_name: another_example_file.png
#     link_text: Example image for this unit.

---

While they are often thought of as the same thing, Git and GitHub are really two different things. Git is a 
versioning system. GitHub is a website that uses Git to facilitate collaboration and project management. Git is open source and free. GitHub
is a commercial enterprise, although the basic level of service is free. Also while collaborting with Git through GitHub
is a very powerful tool, we'll also see GitHub provides a number of other features that allows even more powerful collaboration
and publishing of your work.

At its core, GitHub just hosts a lot of individual repositories, just like the one you have been working with on your local computer. A Git
repository on GitHub isn't any different than the one on your own computer. It feels different because there is a website built around it, and 
also by convention we treat it differently. For security and ease of access, we kind of treat a GitHub repository as a server, but its not. 
Much of how we interact with GitHub is by convention. Over time users, and GitHub have found the best ways to interact with it, the best
workflows and other best practices. 

We refer to a repository that is local as our **local repository** or sometimes **working repository**. Any other repository is
referred to as a **remote repository**.


## Our First GitHub Project

Working with GitHub usually involves at least two repositories, the local repository, and the remote repository on GitHub. There are two ways to get started with any project
using GitHub. The first being local first, where you have a local repository, create an empty GitHub, remote
repository and copy your local repo to GitHub. The other way is create a GitHub repo first and **clone** it to your local computer. Since we already
have a local repository lets do that first.

In either case you will need to create a GitHub repository. 

1. At the GitHub website click **_New_** <img src="/assets/img/getting_started_with_github/start_project.png" width="36" alt="new button"> 
(or **_Start a Project_**) <img src="/assets/img/getting_started_with_github/new_project.png" width="96" alt="Start a project button">. 
2. Give your repository a name, usually the same as your local repository but it doesn't have to be. 
3. It is good, but optional to give it a description. 
4. Choose the public option. You have to pay to make private repositories.
5. Go ahead and make a README. It is always a good idea to have a README. 
6. You can also choose a license too if you want. 
7. Also create a .gitignore.
8. Click the green **_Create Repository_**. GitHub does a pretty good job at suggestion best practices, and its usually a good idea to follow them.
 
If you already have a local repository go to **Linking a Local Repository**, otherwise go to **Cloning a Repository**.
if you don't have a local repository yet.

## Linking a Local Repository





On your new repository landing page you should see a green **_Clone or download_** button. Click that, if it says "Use HTTPS" click that. 
You should see a url that looks something like `https://github/<user_name>/<repo_name>.git`.. Copy it to your clip board and on your local machine, 
enter the following in your terminal.


<img src="/assets/img/getting_started_with_github/clone_expanded.png" alt="Clone or download with https." width="400">


> NOTE: HTTPS and SSH cloning both work. HTTPS is usually easier UNLESS you have set up two-factor
> authentication  (2FA) in GitHub, then HTTPS will not work. In that case, you need to set up 
[SSH keys](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) for your local repository
> and [register them in GitHub](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account).


Now you need to tell your local repository where your remote repository in GitHub is. In your terminal do the following.



> git remote add origin https://github.com/<user_name>/<repo_name>.git
> git remote -v 
  # origin  git@github.com:olendorf/github_for_researchers.git (fetch)
  # origin  git@github.com:olendorf/github_for_researchers.git (push)
  
```

This might be a bit confusing. A remote is a stored location somewhere on the internet. A remote has two parts, a name, and a URI (or URL).
The remote name can be any valid name. No spaces and by convention we use hyphens instead. . By convention, GitHub is called *origin*, 
you could also call it *github*. The URI is what you copied from GitHub and tells git where to look on the internet. The second command 
`git remote -v` lists all the remotes we have created, the `-v` options telling it to be verbose and list the locations too. 
Ignore *fetch* and *push* for now.

Now we do a little Texas Two-Step to so that our local and remote repositories are copies. 

```bash 

> git pull origin master  # you may have to add --allow-unrelated-histories
## OR ##
> git pull origin master --allow-unrelated-histories

  # git pull origin master --allow-unrelated-histories
  #  Response will very some.
  # From github.com:olendorf/learning_git
  #  * branch            master     -> FETCH_HEAD
  # Merge made by the 'recursive' strategy.
  #  .gitignore | 242 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
  #  LICENSE    | 201 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
  #  2 files changed, 443 insertions(+)
  #  create mode 100644 .gitignore
   # create mode 100644 LICENSE
> git push origin master
  # Enumerating objects: 13, done.
  # Counting objects: 100% (13/13), done.
  # Delta compression using up to 4 threads
  # Compressing objects: 100% (12/12), done.
  # Writing objects: 100% (12/12), 3.12 KiB | 3.12 MiB/s, done.
  # Total 12 (delta 4), reused 0 (delta 0)
  # remote: Resolving deltas: 100% (4/4), done.
  # To github.com:olendorf/learning_git.git
  #    f2bc922..9aacf91  master -> master
  
```

The first command `git pull origin master` tells Git to take what ever is in the remote named origin, on the master branch, and merge it with 
your local repository. It works pretty much the same as merging to branches in your local repository together. The `git push origin master` 
is the reverse. It takes the master branch of your local repository and merges it with the master branch on the remote. You can push or pull any branch,
and if one doesn't exist, it's created for you. 



## Cloning a GitHub Repository

If don't already have a local repository, but there is a project on GitHub you would like to work on, you can clone it. This is actually very easy.
Get the repositories URL/URI and on your local machine's terminal enter...


```bash

> git clone https://github.com/<user_name>/<repo_name>.git

> get clone https://github.com/NCSU-Libraries/ncsu_apprentice.git

```

You can get the URI by clicking on the clipboard icon on you get when you click on the green **Clone or download** button.

That's it! It's easier than dealing with an existing repository, but in practice both methods are common.

## Forking A GitHub Repository

There is still another way to create a repository. You can **Fork** someone elses repository to your own account that you can 
then modify independently. There are two reasons to fork a repository. First, you may want to make a contribution to their work. 
In which case, you would fork the repository, make the changes you like, then submit a **pull request** to the original 
repository that will allow the owner to incorporate your changes if they so choose. The other common scenario is that
you would like to use the repository as a jumping off point for your own project. Often these repositories are templates created 
just for that purpose.

Forking a repository is easy. Go to [this repository](https://github.com/NCSU-Libraries/ncsu_apprentice). Click the fork 
button <img src="/assets/img/getting_started_with_github/fork_button.png" width="60">. Choose your own account, and in a few 
seconds you will have a copy of it. 


## Try It Out

You actually know most of what you need to know to work with GitHub on your own. For the most part working with GitHub. You work locally 
making commits when appropriate. Also making branches and merging as well. Then pushing work to GitHub, pulling work as others add it.

- Make edits in your local repository and push it up to GitHub
- Make a new branch, make some edits and send it up to GitHub
- Try making some edits using the GitHub UI and pull it back to local
- Spend some time exploring, see what works and what doesn't







