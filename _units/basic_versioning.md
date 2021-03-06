---
layout: page 
title: Basic Versioning

order: 10 

<<<<<<< HEAD
duration: 15
=======
duration: 10
>>>>>>> 09837dba050835ed134a8870ebe9749ae7c64a26

tutorial: true
instructors_notes: true

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  The heart of Git is versioning. In this unit we'll create a basic text document. Make some changes and track those
  changes using the Git command line tool.

instructors_note: |
  1. Create a repository
  2. Create a simple text document
  3. Commit 
  4. Edit it
  5. Commit
  6. Edit it
  7. Commit
  8. Look at the log
  9. revert back changes
  

  
# These should resolve to files in the supporting_files directory
# or if you specified a different one in _config.yml use that.
# The link_text can be anything you want.
supporting_files:
- file_name: first_example_file.txt
  link_text: Example file  for this unit.
---

## Versioning a text file.

Git versions any kind of file. However, text based files (text, computer code, xml, html etc) work especially well with Git.
This is because Git keeps track of the line by line differences as well. In this unit we will use the sample text files to 
learn the basic, most comman and probably most useful commands in Git.

To get started make a new directory called "learning_git" and navigate to it.

```bash

> mkdir learning_git
> cd learning_git

```
    
Then download the Supporting file [**_Example file_**]({{ site.supporting_files_path }}first_example_file.txt) 
for this unit" into this directory.



Now we are going to make our first Git repository.

```bash

> git init
# Initialized empty Git repository in <your location>
> git add -A
> git commit -m "initial commit"
[master (root-commit) 6a074a6] initial commit
#  1 file changed, 73 insertions(+)
#  create mode 100644 example.txt
> 

```

The last three steps did a few things and are a typical way of creating a new repository. First we **initialized** the repository.
If you type `ls -al` into your terminal you will see it created a `.git` directory. The second two steps almost always go together. 
We first **stage** our changes, with `git add`, the `-A` tells git to stage all changes. The `commit` command creates the new version. You
are required to provide a commit message with every commit with the `-m` option. It's usually a brief, description of the changes made 
in that commit.




Now makes some edits to your text file using any text editor. Try adding lines and workds, deleting things. Then check your status.

```bash

> git status

# You should see something like this

# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)

# 	modified:   first_example_file.txt

# no changes added to commit (use "git add" and/or "git commit -a")

```

The `status` command can be useful if you lost track of where you are at and want to see all the changes you made. As you can see
it gives you some hints as to what to do next as well. Also notice there are other options than `-A` for the `add` command. You can
specify a file or directory as well. The `git add .` for instance will add all the files in your current directory including 
any subdirectories and their contents.

You can also see the changes you've made.

```bash

> git diff
  # diff --git a/first_example_file.txt b/first_example_file.txt
  # index 4030ec8..5cae1d0 100644
  # --- a/first_example_file.txt
  # +++ b/first_example_file.txt
  # @@ -27,4 +27,6 @@ paleo actually farm-to-table aute gastropub pork belly cred in minim yr.
  #  Oh. You need a little dummy text for your mockup? How quaint.
  #  
  #  
  # -Here are some edits in the new branch.
  # \ No newline at end of file
  # +Here are some edits in the new branch.
  # +
  # +These are some edits.
  # \ No newline at end of file

> git add -A
> git commit -m "trying out comitting changes."


```
    
Believe it or not, this is most of what you do with Git. The rest of the tutorial is of 
course important and much of it necessary, but `git add` and `git commit`  are
probably the most often used commands. We can do a little more with commits.




## Try It Out

Practice editing your file, editing, changing and adding text. Also try adding additional 
text files or files of other types. Use the `status`, `diff`, `add` and `commit`
commands.





    
    
    



