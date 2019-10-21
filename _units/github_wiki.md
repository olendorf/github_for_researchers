---
layout: page   
title: GitHub Wiki   

order: 50

duration: 15 

tutorial: true
instructors_notes: true

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  Each GitHub project comes with its own Wiki. This is very handy for extended documentation, 

instructors_note: |
  This is pulled from `page.instructors_note`, and combined with the 
  `page.description` field.
  
  This is not shown in the tutorial pages because `page.tutorial: false`.
  

  
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

Since its beginning GitHub as provided a Wiki to go along with each project.  Wiki's are an easy way to publish content to the web. If you go to your project's Wiki you will
see a green **_Create the first page_** button. You can click that and get started. It gives you an editor and a preview tab. GitHub wikis use
[GitHub Flavored Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). Markdown is a simple way to create good looking web pages. They won't generally 
be as complex as with HTML but it allows you to create content much faster. You can also mix in HTML if you like as well. GitHub flavored markdown just adds a few bells and whistle 
that are especially geared towards software projects. You can use other systems by changing the options in the **_Edit mode: _** drop down. 

## Try It Out

Use the cheat sheat linked above to create a few pages in your Wiki. 

> HINT: You can easily add pages by creating a link with the path to the page you want. 

``` markdown
Some writing [new page text](new-page-path)

```

