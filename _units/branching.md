---
layout: page   # This is required
title: Branching   # This is required

order: 20

duration: 15 

tutorial: true  # 
instructors_notes: true  

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  - Learn how to create and delete branches
  - Learn how to navigate branches
  - Know how to merge branches
  - Understand some of the uses of branches

instructors_note: |
  1. Create a new branch
  2. Edit it 
  3. Move back to master
  4. Create another branch edit it another way.
  5. Merge branches.
  

---

Git allows us to create copies of our work called branches. These branches can be developed
independently, merged back into our main branch or pruned if need be. They are often used in 
collaborative projects to allow collabortors to work independently then 
merge their work. Branches can also be distinct releases of a product, say editions of a book or 
variations of a manuscript. While relatively simple, entire PhD theses have been written on 
workflows based on Git branches and their relationship with GitHub and other related services.

## Create a Branch

Creating a branch is pretty easy, but the command is not entirely untuitive. You 
create a branch with `git checkout -b <branch-name>`. The branch name can be just
about anything so long as it follows these rules.  Branch names cannot begin with a dot ".",
have double dots, "..", have the characters "~", "^", "\" or a space " " anywhere. Nor can they
end with "/" or ".lock".it is typically best to name the descriptively. Have a look at this
[stackoverflow discussion](https://stackoverflow.com/questions/273695/what-are-some-examples-of-commonly-used-practices-for-naming-git-branches) 
for some thoughts on how to best name branches.

```bash

> git checkout -b new-branch # new-branch can be any valid branch name
  # Switched to a new branch 'new-branch'
  
```

This creates a new branch and moves you onto that branch. You can list your current branches.

```bash

> git branch 
  # master
  # * new-branch
  
```

Notice the asterisk __*__ denotes your current branch.

## Navigating Branches

Move between branches with the `checkout` command without the `-b` option.

```bash

> git checkout master
  # Switched to branch 'master'
  
```

Lets move back to the *new-branch*. Edit your text file again. This time add some text to the bottom of the file. 
Once you are done, stage and commit your changes.

```bash

> checkout new-branch

## Make your edits.

> git stage -A
> git commit -m "made some edits in new-branch"

```

Keep your eyes on your text editor, and switch back to your *master* branch.

```bash

> git checkout master

```

You will see those changes are NOT in your master branch. You can view the differences using the **diff** command.

```bash

> git diff new-branch master
# you will see the differences between the branches.

```

### Merging Branches


Merging is usually very straightforward. 

```bash 

> git merge new-branch 

```


If you look at your text editor, you should see the changes you made again.

### Deleting A Branch

If you don't need that branch anymore you can delete it now. When you list your branches, you'll see its gone.

```bash

> git branch -d new-branch 
> git branch
  # * master

```

## Try It Out

1. Practice making branches, editing your files, commiting those changes and merging branches. Don't be afraid to test the limits a bit. 


2. Try making two new branches, `foo-bar` and `foo-baz`.  Change `Lorem ipsum` in the beginning of the file to different things in each branch. 
Merge both into master (not into each other). What happens?



> HINT: If you get a merge conflict, go to the file indicated. You will see the alternative edits set off with <<< and ====. Edit the file to reflect 
>       what you want.
>       Fixing merge conflicts is usually not that hard. Just edit the file to have what you want, then commit it. 
>       It can be very hard if you have large complicated commits though. Another reason to commit often!






