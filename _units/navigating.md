---
layout: page   # This is required
title: Navigating Branches and Commits   # This is required

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
- file_name: another_example_file.png
  link_text: Another Example image for this unit.

---

Sometimes we need to do some slightly more complicated interactions with our git version tree.
This especially happens when we have made some mistakes that we have to deal with. Maybe we 
haven't been careful about committing changes often enough, or even just made a huge mess of things.
Fortunately only in the worst situations is most of your work not recoverable, and only if you have 
been very negligent in your committing and branching. 

## Going back to your last commit.

Its not unusual to realize your work has gone a bit awry. If you commit often, its often the best course of action to go back to your 
last commit. First lets add another file. Downlaod the sample file and put it in your `learning_git` directory. Then also, open 
up your text file and make some edits.

**OH NO!** You made a horrible mistake! Let's walk it back. So there are the edits you made. If you `git status` you will see that you 
have made the changes to your text file, and also you created the image file. So lets roll back those changes.

```bash
> git rest --hard
```

You will see that your text changes are gone. But the new file is still there. For this we need another command.

```bash
> git clean -fd
```

Now you are back where you started from your last commit. In fact, it was used few times just in writing this tutorial!

