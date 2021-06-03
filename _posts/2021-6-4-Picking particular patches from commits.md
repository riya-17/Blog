---
layout: post
title: Picking particular patches from commits
---
![_config.yml]({{ site.baseurl }}/images/giphy.gif)

Hello world,

<h5>Main Heading</h5>

- list

<h3>Header2</h3>

**bold** 

Step-1 - git reset HEAD^
	This will move the files from the topmost commit to “to be added/files that changed” state.

Step-2 - git add --patch file_name.py (file name from the listed files) 
	This command displays each the patch of code and we can split, select, leave, etc from the code with the help of following options 
	After this there are many options we can choose from like
	Y - yes
	N - no
	S - split
	Q -
	A - 
	D - 
	J - 
	J - 
	G - 
	/ - 
	E - 
	? - 

Step-3 - After selecting the patch of code we want to add to a particular commit. Commit that file with a new commit message

