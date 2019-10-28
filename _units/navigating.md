---
layout: page   # This is required
title: Navigation and Manipulation  # This is required

order: 23

duration: 15 

tutorial: true  # 
instructors_notes: true  

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  Sometimes we need to do some slightly more complicated interactions with our git version tree.
  This especially happens when we have made some mistakes that we have to deal with. Maybe we 
  haven't been careful about committing changes often enough, or even just made a huge mess of things.
  Fortunately only in the worst situations is most of your work not recoverable, and only if you have 
  been very negligent in your committing and branching. 

instructors_note: |
  1. Create a new branch
  2. Edit it 
  3. Move back to master
  4. Create another branch edit it another way.
  5. Merge branches.
  

  
# These should resolve to files in the supporting_files directory
# or if you specified a different one in _config.yml use that.
# The link_text can be anything you want.
supporting_files:
#   - file:
#     file_name: first_example_file.txt
#     link_text: Example file  for this unit.
- file_name: example_file_2.png
  link_text: Example file 2.

---

Sometimes we need to do some slightly more complicated interactions with our git version tree.
This especially happens when we have made some mistakes that we have to deal with. Maybe we 
haven't been careful about committing changes often enough, or even just made a huge mess of things. Also
as we'll see in future units, having more collaborators often requires some tree navigation and manipulation.
Fortunately only in the worst situations is most of your work not recoverable, and only if you have 
been negligent in your committing and branching. 

## Going Back to Your Last Commit.

Its not unusual to realize your work has gone a bit awry. If you commit often, its often the best course of action to go back to your 
last commit. First lets add another file. Download the [example_file_2.png](/supporting_files/example_file_2.png) and put it in y
our `learning_git` directory. Then also, open up your first example file and make some edits.

**OH NO!** You made a horrible mistake! Let's walk it back. If you `git status` you will see that you 
have made the changes to your text file, and also you created the image file. So lets roll back those changes.

```bash

> git reset --hard

```

You will see that your text changes are gone. But the new file is still there. For this we need another command.

```bash

> git clean -fd

```

Now you are back where you started from your last commit. In fact, it was used few times just in writing this tutorial!

## Going Back to a Specific Commit

Sometimes you may have to go back further than your last commit too. You can do this too. First you need to find the commit you want. 

```bash

> git log
  # You should see a list of yoru commits. Hit return to scroll through.
  # commit 4a04c5e359539fab014b497706ea8cae942de70d
  # Author: Robert Olendorf <myemail@example.com>
  # Date:   Sun Sep 15 13:56:07 2019 +0000

:
  
```


There shouldn't be too many commits. If you want to make a few more just change a thing, stage and commit a few times. Once you are ready, 
find a commit you want to rollback too. Git identifies these with an MD5 hash, _4a04c5e35..._ in this case (yours will be different). You don't have to type the entire 
thing though, just the first 6-8 characters will usually do. You can see what that branch looked like first. Your checksum will differ.

```bash

> git checkout 4403fe02
  # Note: checking out '4403fe02'.
  # 
  # You are in 'detached HEAD' state. You can look around, make experimental
  # changes and commit them, and you can discard any commits you make in this
  # state without impacting any branches by performing another checkout.
  # 
  # If you want to create a new branch to retain commits you create, you may
  # do so (now or later) by using -b with the checkout command again. Example:
  # 
  #   git checkout -b <new-branch-name>
  # 
  # HEAD is now at 4403fe0 Initial commit
  
```

You can go back to your master branch and reset to that commit with the following.

```bash

> git checkout master
> git reset --hard  4403fe02

```


### Catching Your Branch Up With The Base Branch

If you are careful and make branches with your new work, you should rarely have to walk back more 
than one commit. More common on large projects with lots of collaborators you will need to move the base branch 
up to your working  branch to get the most recent work. This is called **rebasing** and is pretty much a merge, but
is used to move a working branch's history up so that it contains the most recent commits from a base branch. If you don't have
a branch off master make one now. Then go back to *master* and make a few changes and commits.

```bash

> git checkout new-branch
> git rebase master
  # First, rewinding head to replay your work on top of it...
  # Fast-forwarded new-branch to master.
  
```

## Try It Out

Try making a number of commits, then walking them back. Make some changes to your master branch and rebasing a side branch. 








