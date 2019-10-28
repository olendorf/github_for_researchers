---
layout: page   # This is required
title: More Collaboration  # This is required

order: 35

duration: 15

tutorial: true  # Set to true if you want this page displayed as a web page
instructors_notes: true  # Set to true if you want this displayed in instructors notes

description: |
  This section expands on collaborating to introduce collaborating with people even if they
  aren't listed as collaborators.

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

One of the best things about GitHub is that is not only allows you to collaborate within your team, but it allows anyone else
to potentially contribute to your project as well. The culture around GitHub revolves around open source, and community 
contributions to projects. There are a couple ways you can contribute to projects, including this tutorial!

## Submitting Issues

This is the easiest way to contribute to a project. Look at one of your neighbor's repositories, preferably one you aren't collaborating on.
Click on the **_Issues_**. You can add an issue by clicking **_New issue_** and filling out the simple form, you should provide a desriptive title
then more detail in the comment. It uses markdown so you can format it, and you can also add files and pictures.

Issues are used for many things. Within a project team, they are often used to manage tasks, describing what needs to be done, and assigning them 
to team members. 

In addition, you can contribute to any project with issues. Just go to their issues page, and if they allow it, submit an issue. Typically,
these will be feature requests, bugs and errors, or even just questions. The good thing about this, is that all this communication is saved so that others can use the information. It
is also very well indexed by the search engines as well.

## Submitting a Pull Request

If you are really feeling helpful or motivated, you can also contribute directly to a project via a pull request. Of course you have already learned 
about pull requests, but not how to do them when you aren't a collaborator. There is just one more thing to learn to do this. You need to **_fork_** the repository. 
This is another way to make a copy of a repository. 

Go to this [test repository](https://github.com/olendorf/hellogitworld.git) and click on the **_Fork_** button. It may ask you where to put it, 
just choose your own account. Now you have your own version of my play repository (which I forked from someone else!). Makes some edits and commit them. 
Now you can make a pull request. Click **_Pull requests_**, then click the green **_New pull request button_**. Set the base repository to *olendor:learning_git*, and 
use the *develop* branch. Set the compare to your repository and the develop branch. Click **_Create pull request_** and give a nice title and description. Click  **_Create pull request_** again 
and the requst will be posted to the repository. 

At this point, the repository owner or maintainer will review your changes. Any questions will be posted as comments on the pull request issue, and ideally answered by you. Once everything is
acceptable, the changes will be merged into the project. Again, all the of this is recorded and typically web searchable too. You also become a contribute to the repository so you get
recognition for your work.

