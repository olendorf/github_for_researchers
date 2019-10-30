---
layout: page   # This is required
title: GitHub Pages   # This is required

order: 60

duration: 10 # A hint to how long it will take to cover this topic in mintues.

tutorial: true  # Set to true if you want this page displayed as a web page
instructors_notes: true  # Set to true if you want this displayed in instructors notes

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  GitHub also provides a *FREE* static web page platform. You can use this for just 
  about anything. Common use cases are documentating projects, personal web pages and html 
  slides from talks.
  
  Publishing on GitHub pages really requires its own tutorial (coming soon?). Here we will
  just publish a simple page based on the content we have already created.

instructors_note: |


  
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

If you want more of a web page feel than a Wiki can give you, GitHub also allows you to 
generate static web pages. This workshop and tutorial are actually devlivered via GitHub
pages. A full tutorial on GitHub pages is far beyond our scope here, 
but to try it out quickly. 

Create a new branch called **_gh-pages_**.

Create a file called `index.md` and add the following lines.

```markdown

## Hello world.

This is my first GitHub Pages page!
```

Then go to your project settings and scroll down to the GitHub pages section. You will see a notice, and once its green and 
says its published, follow the link to your new page.

<img src="/assets/img/github_pages/gh-pages_status.png" alt="Status display for github pages" width="900" />

If you read the [documentation](https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages) you will see there are other ways to organize your GitHub pages as well. 

There is a lot you can do with GitHub pages. Not only do people write documentation for their projects, but you can put personal websites up, presentation slides, even this tutorial 
is done on GitHub pages!.






