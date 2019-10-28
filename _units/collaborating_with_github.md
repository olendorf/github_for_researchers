---
layout: page   # This is required
title: Collaborating With GitHub   # This is required

order: 30

duration: 20

tutorial: true  # Set to true if you want this page displayed as a web page
instructors_notes: true  # Set to true if you want this displayed in instructors notes

description: |
  One of the biggest benefits of GitHub is how it facilitates collaboration on a number
  of different levels. Over the years, a culture has grown up around GitHub that specifies 
  several conventions that facilitate collaboration. In this unit, you learn how to 
  add collaborators and work with them on a single repository.
  
  In this section, we will learn how to copy repositories, add collaborators
  to our own repositories and even collaborate with people we may not know at all. 

instructors_note: |
  This is pulled from `page.instructors_note`, and combined with the 
  `page.description` field.
  

  
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

## Add A Collaborator

Collaborators are typically people who are on your team working directly on the project. As we'll see in the next unit
its also possible to let people collaborate without directly adding them as collaborators. You should only add people 
as collaborators that you know and trust.

Any collaborator needs to have a GitHub account. Once they have one, have them give you their user name and you can add them. Add one 
of your neighbors to your practice repository this way. On the GitHub website go to your project's settings (not your personal settings). Click
on the **_Collaborators_** tab on the left. Add your neighbor to your project. They will have to go to their email and accept the invitation. Once that is 
done if you refresh the page you should see them listed.

> PRO TIP: Having a distinct avatar really helps a lot in managing projects. The randomly generated shapes are hard to recognize. It doesn't have
>          to be a picture of you, but something easily recognizable. On that note, landscape pics are not very good either.

Now you should be a collaborator on a neighbor's repo and they should be a collaborator on yours. Now you can clone their repository 
and edit theirs just like you did your own.

```bash 

> cd ..    # move out of your previous project if necessary.
> git clone https://github.com/<other user name>/<repo name>.git   # close the repo
> cd <repo name>   # move into the new project directory.

```

Once you have collaborators, you can start collaborating! You know almost everything you need to know to collaborate now. 
We'll introduce a couple new features that help you collaborte. Then we'll move on to managing your collaborations to maximize efficiency and minimize problems.

## Pull Requests

Pull requests are just a formal way of doing a merge. It is specific to GitHub, (i.e. not part of Git). Pull requests provide mechanisms and protections

to control how branches are merged among collaborators and provide opportunities for quality control and review.

To start, go to your terminal, and create a new branch in the local repository you clone from your neighbor. Make some edits, then push that branch up to GitHub.

```bash

> git checkout -b pull-branch
# ...
# makes some edits
# ...
> git add -A
> git commit -m "learning a pull request"
> git push origin pull-branch 

```

Go to the GitHub repository. Most times you should see a yellow banner with a green button **Compare & pull request**. Click that and set the 
dropdown for **_base: master_**. Make sure the other one says **_compare: pull-branch_**. The comment is optional but a good idea. Notice there 
are options to assign reviewers and asigness (the person to do the actual merge). The other options we'll touch on later. Click **_Create pull request_**. 


<img src="/assets/img/getting_started_with_github/pull_flash.png" alt="Flash message for pull request." width="800">


This doesn't actually merge it yet. It does just what it says, it creates a **_pull request_**, which is a suspended merge. If 
you click on the *Pull Requests* tab, you see this request. You'll see references to reviews, the changes proposed in this request, and 
also that there are no merge conflicts. Although there are other tests that can be performed here as well, its beyond the scope of this tutorial. 
The important thing is by merging via a pull request, we can ensure that our project maintains a high standard of quality.

Once you have decided everything looks good, you can merge the branch. Click the green **_Merge pull request_** button, then click **_Confirm merge_**. 
You will see **_Pull request successfully merged and closed_**. The merged part probably makes sense, but why closed? This is because a pull 
request is both a merge, and an issue. We haven't covered issues yet. Briefly, issues is a GitHub feature that allows you to manager your 
projects using a ticketing system. Issues can be assigned to people, labeled, commented on and closed when complete.


The last thing you need to do is to bring these changes back to your local repository. Then you can also delete the feature branch.

```bash

> git checkout master
> git pull origin master
> git branch -d pull-branch 

```

And finally delete the branch in GitHub. You should see this option on your Pull Request page, but if not you can list your pull requests and delete it there.



## Managing Your Collaboration


While being able to work with others and combine their work with yours is powerful, it can also quickly lead to confusion and chaos if not managed properly. Next we'll cover 
some of the basic principles of collaborating with Git and GitHub. 

You have already added a collaborator, and this is the most basic way of managing collaborations. The primary way to manage collaborations is to manage how your branches 
are merged. If you go to settings, and click on the **_Branches_** tab, you'll see you can set your default branch, and set up Branch protection rules. We'll be exploring these 
options and discussing some strategies to get the most out of your collaborations.



### Branching Rules and Models

One of the first decisions you will need to make is how you will manager your branches. There are lots of ways to do it, but if you look at this 
[commonly used model](https://nvie.com/posts/a-successful-git-branching-model/) you will see some of the most important concepts.

#### Protect your main branches. 

One of the fundamental principles is to keep one or two branches "safe". By convention, the **_master_** branch is always what people will look at to use 
your work. So keep your **_master_** branch production ready as much as possible. Many software projects keep a **_develop_** branch too. This branch is also 
highly protected. Often work is collected in the **_develop_** branch. Then further testing is done before its merged into the main branch for the release. 

Create a develop branch in your local repostiory then push it up to GitHub.

```bash

> git checkout -b develop
> git push origin develop 

```

Now go to the settings of your GitHub repository, and click the **_Branches_** tab. You will see an option to set the default branch. Set it 
to **develop** and then **_Update_**, then confirm this is what you want to do. Now, by default, all pull requests will go to the **develop** branch. 

You can also set up rules for merging pull requests. If you click on the **_Add rule_** button by Branch protection rules, you'll get a form 
to do this. There is a lot here. The first thing is to define what branches the rule applies to. If you type in `develop`, check 
**_Require status checks to pass before mergin_** and then **_Save_** it will apply to your develop branch. We'll leave it to you to 
explore this more in *Try It Out*.


#### Simplicity is important

While the model linked here may seem complicated, its actually quite simple. The rules outlined, make sure that branches are only created from 
**develop**, and merged back into **develop**. Branches are typically only created with a specific purpose, such as developing a new feature, 
fixing a bug. You can also use them to publish variations of the same thing. For instance, in a research project where you publish several papers 
off of one data set, you could make a branch for each publication. Also, these rules only apply to branches that are pushed up to GitHub.
Creating your own side branches locally to try things out and merging it onto your working branch is common.


#### Only merge functioning branches

Or perhaps more clearly, don't merge branches that aren't working. Of course you can't catch everything, but that is the goal. One way to help ensure this is to have one person.


## Try It Out

Collaborating with a team takes some communicaton. Work with your neighbor with one of your repositories to come up with a plan for branching and merging. 
Try out some of the different rule settings in the branch protection rules too. Then each of you practice by creating branches off of develop, making edits, 
pushing them up to GitHub. Then create and merge pull requests. 







