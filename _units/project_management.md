---
layout: page   # This is required
title: Project Management   # This is required

order: 43   # Determines the order of units. Doesn't need to be consecutive though
            # or even start with zero, the pages will be displayed in their sort
            # order.

duration: 10 # A hint to how long it will take to cover this topic in mintues.

tutorial: true  # Set to true if you want this page displayed as a web page
instructors_notes: true  # Set to true if you want this displayed in instructors notes

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  GitHub's project management tools are some of the most recent and most useful tools 
  of GitHub. Some people don't even use the versioning and just use the project 
  management tools. For instance, one person managed the renovation of their house
  using GitHub issues and GitHub Projects.

instructors_note: |
  Just give a tour of the service. Give a little time to play with Github Projects.
  

  
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

Larger projects, with several collaborators, lots of files and other moving parts can be difficult to 
manage. Fortuntely there are several tools that GitHub provides that can help a lot with projects
management. There are also several third-party applications that you can use as well.


While GitHub is developed initially for software development teams, the project management tools introduced here are useful for a wide range of projects. People 
have even used these tools for projects as diverse as designing a car, to renovating a house.


## GitHub Issues

Project management with GitHub revolves around issues. Issues were already introduced as a way of collaborating. Often they are used
to ask questions or report bugs about a project. However, they can also be used to manage projects. To use issues to manage a project, you 
often start by deciding some of the bigger sub-projects that will go into your project. Some of these sub-projects will need to be done first, others done after,
and so on. Then you can break those larger sub-projects into smaller bits of work, ideally bits of work that can be done by one person in a day or two.

The description and comments in an issue use markdown, so you can put a fair amount of formatting into them. You can attach other files, and you can even create checklists 
in them. If you make a checklist in an issue, GitHub automatically provides a progress bar for it.

```markdown

This is a new issue that isn't ready yet


# This is a checklist

- [ ] Task 1

- [ ] Task 2

- [ ] Task D

# This is a link to issue number 2
#2

```

Sometimes an issue will refer to another issue. Maybe the other issue needs to be done first, its somehow related, or maybe even a dupilcate. You can easily 
link issues by using the syntax `#<issue number>`.



### Assignees

Once you have an issue that represents a doable piece of work, you need to decide who will do it. Assignees are the people who are responsible for completing
the work. By assigning collaborators to an issue, you make it easy for them to know what to do. You also help prevent multiple people from doing the same tasks.



### Labels

Labels are a very general purpose tool. Each issue can be assigned any number of labels. Some teams use them to label the status of an issue (reaady, in progress, done), 
or to describe the general type of work to be done (data collection, analysis, documentation). With a little care and though, labels can help a lot in organizing and searching 
your issues.


### Milestones

Milestones are a bit like labels, except that you can set a date for completion. Also, as you add issues to them, you get a progress bar as well. Unlike labels,
you can only add one milestone to an issue.



## GitHub Projects

GitHub Projects uses the issues you have created above to create a Kanban board. Kanban boards are a commonly used tool in project management. The idea 
is that each issue functions like a card that can be moved around. Typically there are swim lanes such as "Ready", "In Progress" or "Done". Additionally, the cards can
be moved up and down within a swimlane. Usually the cards toward the top are higher priority and should be done first. As an issue 
is worked on it can be moved to the appropriate swim lane. This allows project managers to track progress, and others to easily communicate what they have done,
what they are working on and what they will do. 

<figure>
  <img src="{{ site.baseurl }}/assets/img/project_management/github_project.png" alt="Just a sample image" style="width: 900px"/>
  <figcaption>An example Kanban board from a GitHub project</figcaption>
</figure>

A GitHub repository can have mulitple projects and an issue can belong to multiple projects. However, simplicity usually works best!


## ZenHub

[ZenHub](https://app.zenhub.com) is an alternative to GitHub Projects. It's a third party application that uses GitHub's APIs to create a Kanban board. It has a few
bells and whistles not found in GitHub Projects, especially involving linking issues together. ZenHub has the concepts of **Epics**, **Dependencies** and work **Estimates**.

**Epics** are issues that are too big to be done in just a day or two and are composed of several typical issues. This is very useful in planning a project as it is often easiest to
think in terms of large chunks of work, then decompose those into smaller doable issues. 

**Dependencies** are issues that either block another issue from being completed, or are being blocked by another issue. By noting these dependencies, it can
be easier to prioritize what work to be done.


**Estimates** are a way of determining how much work a particular issue might take. Typically this is estimated by a team in meetings. The numbers are relative and highly subjective. An estimate
of 1, for instance, by be just an hour of work in one project, but 2 days in another project. Smaller issues are usually easier to estimate the time. For instance, if you are renovating your kitchen,
its pretty easy to estimate how much time to tile your floor, but it might not be as easy to estimate how much time total the renovation might take without breaking up the project into smaller chunks.







