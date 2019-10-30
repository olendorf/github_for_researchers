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
  - Learn how to move between commits
  - Learn three two ways to undo work

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

## Undoing Uncommited Work

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

You will typically checkout previous commits while trying to figure out where your last good commit was made, or while
tracking down the origin of some bad work. Once you have found the commit you want you can revert it.



## Revert To A Previous Commit

Ideally you never commit work that isn't perfect. In the real world you never commit work that isn't perfect. Sometimes
the best way to fix that is to revert to a previous commit. Git gives us the `revert` command for that.

```bash

# Make some edits.
> git add -A
> git commit -m "one commit"
# Make some edits.
> git add -A
> git commit -m "two commit"
# Make some edits.
> git add -A
> git commit -m "three commit"
# Make some edits.
> git add -A
> git commit -m "four commit"

> git log
# Get the MD5 hash of "two commit"

> git revert df1eb3006

```

Revert doesn't actually roll back all your other commits. In Git, it is considered very
bad to rewrite history. Instead it takes the commit you specify, and puts that state 
in front of the commits your rolling back. Conceptually, your tree would look
something like 

**one commit** -> **two commit** -> **three commit** -> **four commit** -> **two commit**

You can verify this by using `git log`.

```bash

> git log
# commit c54730a9384811b4adbc65bd6d902cf6e3c35468 (HEAD -> new-branch)
# Author: Robert Olendorf <drolendorf@gmail.com>
# Date:   Mon Oct 28 12:37:06 2019 -0400
# 
#     Revert "two commit"
#     
#     This reverts commit df1eb3006e7ec1fb3f59dc8fdb40b117b07ab19e.
# 
# commit 33508a1b308c922c2cdf4f564263b2c31065d527
# Author: Robert Olendorf <drolendorf@gmail.com>
# Date:   Mon Oct 28 12:36:58 2019 -0400
# 
#     four commit
# 
# commit 8d38ac1cd60a0bc2167c1c473189b3f78d3c9b53
# Author: Robert Olendorf <drolendorf@gmail.com>
# Date:   Mon Oct 28 12:36:03 2019 -0400
# 
#     three commit
# 
# commit df1eb3006e7ec1fb3f59dc8fdb40b117b07ab19e
# Author: Robert Olendorf <drolendorf@gmail.com>
# Date:   Mon Oct 28 12:35:43 2019 -0400
# 
#     two commit
# 
# commit a027f097535dc9fad416dd681db3db52a87af085
# Author: Robert Olendorf <drolendorf@gmail.com>
# Date:   Mon Oct 28 12:35:20 2019 -0400
# 
#     one commit
# 
# commit 4c396b1742bab9970b3cd1f595e65067fd1e3197
# Author: Robert Olendorf <drolendorf@gmail.com>
# Date:   Mon Oct 28 12:34:33 2019 -0400
# 
#     fo0
# 
# commit 6a074a6f23ce02709ebeeb00dfbc0a66b5fa6a9b (master)
# Author: Robert Olendorf <drolendorf@gmail.com>
# Date:   Mon Oct 28 09:10:54 2019 -0400
# 
#     initial commit


```


## Catching Your Branch Up With The Base Branch

If you are careful and make branches with your new work, you should rarely have to walk back more 
than one commit. More common on large projects with lots of collaborators you will need to move the base branch 
up to your working  branch to get the most recent work. This is called **rebasing** and is pretty much a merge, but
is used to move a working branch's history up so that it contains the most recent commits from a base branch. 

If you don't have a branch off master make one now. 

```bash

> git checkout -b rebase-branch

```

Then go back to *master* and make a few changes and commits.

```bash

> get checkout master
# Make some edits

> git commit -m "first master commit"
# Make some edits.

> git commit -m "second master commit"

```

Then checkout your `rebase-branch` again and do the following.

```bash

> git checkout rebase-branch

> git rebase master
  # First, rewinding head to replay your work on top of it...
  # Fast-forwarded new-branch to master.
  
```

## Try It Out

- Make some changes to your file then `reset` them.

- Try making a number of commits, then walking them back. Make some changes to your master branch and rebasing a side branch. 








