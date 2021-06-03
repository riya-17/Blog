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

What happens when you have to rearrange you commits with some particular changes in your files. Like you have added whole file to a single commit while you just wanted to add four lines of the whole file and rest of the changes you wanted to add in another commit. It isn't much of a headache if it is just a single file and a little of patch to change but the sitution grows scarier when there are a lot many files involven and you have a large number of commits lined up. That does seem scarier isn't it?

Here is one of many solutions that can help.

- git reset HEAD^
	This will move the files from the topmost commit to 'untracked files' state.
	
	Files being in an untracek state consists of all your changes but they are waiting to be added, but you don't wanna add whole file. just some of largely made changes.

- git add --patch file_name.py (file name from the listed 'untracked files') 
	This command will display all the changes that you have made to that particular file patch by patch. We can play around with each patch of the code. We can split, select, leave, etc from the code with the help of following options which will be displayed as soon as you add patch the file.
	
	After this there are many options we can choose from like
	y - yes (you wanna take this whole patch)
	n - no (you don't want this patch in this commit)
	s - split (slipt the patch into lines)
	q -
	a - 
	d - 
	J - 
	j - 
	g - 
	/ - 
	e - 
	? - 

- After selecting the code patch from the file. we can just say 'no' to other patches and get out of the file. We get that file with out selected patches into the "to be commited" state. Commit that file with a new commit message. and you are good to go.

You can add more files and patches the same way.

Happy patching!

