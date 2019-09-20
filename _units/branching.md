---
layout: page   # This is required
title: Branching Versions   # This is required

order: 20

duration: 15 

tutorial: true  # 
instructors_notes: true  

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  Git allows us to create copies of our work called branches. These branches can be developed
  independently, merged back into our main branch or pruned if need be. Branches have many uses.
  They are often used in collaborative projects to allow collabortors to work independently then 
  merge their work. Branches can also be distinct releases of a product, say editions of a book or 
  variations of a manuscript. While relatively simple, entire PhD theses have been written on 
  workflows based on Git branches and their relationship with GitHub and other related services.

instructors_note: |
  1. Create a new branch
  2. Edit it 
  3. Move back to master
  4. Create another branch edit it another way.
  5. Merge branches.
  

---

Git allows us to create copies of our work called branches. These branches can be developed
independently, merged back into our main branch or pruned if need be. Branches have many uses.
They are often used in collaborative projects to allow collabortors to work independently then 
merge their work. Branches can also be distinct releases of a product, say editions of a book or 
variations of a manuscript. While relatively simple, entire PhD theses have been written on 
workflows based on Git branches and their relationship with GitHub and other related services.

## Create a Branch

Creating a branch is pretty easy, but the command is not entirely untuitive.

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

## Navigating Branches

And move between branches with the `checkout` command.

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

The branch is feature can be used for a number of things. 
The most common way is to keep your master branch "clean" with only what you really want. If you are writing computer code, this means only code that is 100% working. For 
other things it would just be what is "correct" or what you want published for instance. You can make branches to try out different things without messing up what 
is in your master branch. Once your *new-branch* is how you want it, you can **merge** it into your master branch.

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

Practice making branches, editing your files, commiting those changes and merging branches. Don't be afraid to test the limits a bit. 


### Advanced
Try making two new branches, changing the same things and merging them both into master (not into each other). What happens?



> HINT: If you get a merge conflict, go to the file indicated. You will see the alternative edits set off with <<< and ====. Edit the file to reflect 
>        what you want.
>        Fixing merge conflicts is usually not that hard. Just edit the file to have what you want, then commit it. 
>       It can be very hard if you have large complicated commits though. Another reason to commit often!






