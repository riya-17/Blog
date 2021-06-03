---
layout: post
title: Picking particular patches from commits
---
![_config.yml]({{ site.baseurl }}/images/giphy.gif)

Hello world,

What happens when you have to rearrange your commits with some particular changes in your files. Like you have added the whole file to a single commit while you just wanted to add a little patch and the rest of the changes you wanted to add in another commit. It isn't much of a headache if it is just a single file and a little patch to change but the situation goes out of hand when there are a lot of many files involved and you have a large number of commits lined up. That does seem scarier. isn't it?

Git consists of some awesome features and Interactive staging is one of them. Git makes it possible to stage certain patches of files and not the rest of them.

Here is one of many solutions:

<br>

- **git reset HEAD^** <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This will move the files from the topmost commit to the 'untracked files' state.<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Files being in an untracked state consist of all your changes but they are waiting to be added, but you don't wanna add the whole file. just some of the largest made changes.

<br>

- **git add --patch file_name.py** (file_name from the listed 'untracked files') <br> 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This command will display all the changes that you have made to that particular file patch by patch. We can play around with each patch of the code. We can split, select, leave, etc from the code with the help of the following options which will be displayed as soon as you add patch the file.
		
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After this there are many options we can choose from like:
	
   - 
     - y - yes (you wanna take this whole patch)
     - n - no (you don't want this patch in this commit)
     - s - split (slipt the patch into lines)
     - q - select a hunk to go to
     - a - you wanna take this and all the remaining patches in the file
     - d - do not wanna take this or remaining patches
     - J - leave this patch undecided, see next patch
     - j - leave this patch undecided, see next undecided patch
     - g - select a patch to go
     - / - search for a patch with the given regex
     - e - manually edit the present patch
     - ? - print help 

<br>

- After selecting the code patch from the file. we can just say 'no' to other patches and get out of the file. We get that file with our selected patches into the "to be committed" state. Commit that file with a new commit message. and you are good to go.

You can add more files and patches the same way.

Happy patching!

