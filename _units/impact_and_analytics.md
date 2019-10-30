---
layout: page   # This is required
title: Impact and Analytics   # This is required

order: 45    # Determines the order of units. Doesn't need to be consecutive though
            # or even start with zero, the pages will be displayed in their sort
            # order.

duration: 10 # A hint to how long it will take to cover this topic in mintues.

tutorial: true  # Set to true if you want this page displayed as a web page
instructors_notes: true  # Set to true if you want this displayed in instructors notes

# Provide a brief description of what the unit is about. You can use markdown
# notation for this.
description: |
  The impact and analytic numbers are useful not only from a project management standpoint,
  but can also help users decide if a project is worth using in their own work.

instructors_note: |
  Show and tell of the different information shown for a project.
  
  

  
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

GitHub provides a number of ways to see the activity and status of a repository. There is 
quite a bit of information just on the splash page. The image below is taken from a 
popular web development framework [Ruby on Rails](https://github.com/rails/rails).

<img src="/assets/img/impact_and_analytics/ror_splash.png" 
     alt="Impact for ruby on rails shown on the splash page" 
     width="900" />
     
Working top to bottom, we first see how many projects are using this framework ( **Used by**, 1.2 million).
**Watchers**, who get updates about the project. **Stars**, that represent people who like the project.
Stars also function something like bookmarks. Finally **Forks**, which we have talked about, that 
are copies of a repository. All of these things give you an idea of how useful and popular a
project might be.

Below that we see the number of open issues and open pull requests. This can give you an
idea of how well the project maintainers are doing in keeping up with bugs, suggested 
features. If you scan through the issues and pull requests you can also get an idea of how fast 
they get handled. The first page of Ruby on Rails issues are mostly just a few hours old 
at the time of writing.

Below that you can see the number of commits, branches, releases and contributes. If you click on the 
colored bar, you will see the languages that appear in the code base for this project. 

Ruby on Rails is a popular and very active  project with lots of contributors and a fairly large base of users. In short,
we can say it has a large, active and supportive community for an open source project.

If you click on the **Insights** tab <img src="/assets/img/impact_and_analytics/insights.png" 
alt="Insights icon" width=70 />, you will be taken to more information about the project.

<img src="/assets/img/impact_and_analytics/insights_pulse.png" alt="Insights pulse view" width="900" />

You can look through the different information on the sidebar. Contributors can tell
you who the biggest contributors are. Commits and code frequency give you more detailed 
information about the activity in the project. The network and forks provide a view into
how the projects branches and forks. 

## Analytics for Project Management

If you are a maintainer or manager for a project, these analytics can be useful for 
making sure your project stays on track. You can also identify potential issues into how
commits, branches and forks are being handled.

## Choosing A Project To Used

One of the most common reasons researchers use GitHub is to use other people's work. You
can use these analytics to help you decide if you can use a project for your own work.
For instance, lets say there is an R package on GitHub you are considering using.

You would first go to the splash page and look at the README. A well maintained and
written README is a good sign. It should give you a pretty good idea how to use the
project.

Then you would look at the activity shown on the file list, the issues and pull requests.
If there has been recent activity and the issues seem to be handled quickly that is also
a good sign. If the last activity was 5 years ago, perhaps it would be better to find
another alternative as this project might be dead (or you could adopt the project as 
your own by forking it.)

Then you might go to the activity pages, look at the collaborator, see when the commits 
where. 

There is no hard and fast rule for when you should use or not use a project. It depends
not only on the status of the project you are considering, but also on what other 
alternatives exists and also your own tolerance for frustration.














