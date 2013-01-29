# git intro for CAEN 

by: otto sipe  
github: @ottosipe     
email: ottosipe@umich.edu  

## quick info:  

* git works by incrementally adding new changes to a repository. 
* as you make changes you run `git add .` to add the changes in the current directory or `git add filname`. 
* once you've added files you can run `git commit -m "your description of changes here"` to make a commit. 
* when you've made a commit (or multiple commits) you can run `git push` to send them to the main repo.
* if changes have been made on a different repo run `git pull` to pull those changes

## quick and dirty if you know git:
in `~/.git` folder on CAEN: `git init --bare eecs280/proj1`  
from CAEN home: `git clone ~/.git/eecs280/proj1/`  
or from remote: `git clone uniqname@login.engin.umich.edu:~/.git/eecs280/proj1`  
first push use: `git push origin master`

## detailed setup on CAEN:

1. login To CAEN  
	`ssh uniqname@login.engin.umich.edu`
2. create a .git folder in your home directory  
	`mkdir .git; cd .git`  
3. create a project repo (PROTIP: use folders for seperate classes)  
	`git init --bare eecs280/proj1`  
	* this command makes a folder called `eecs280` and a repository called `proj1`  
4. go back to your home directory.  
	`git clone ~/.git/eecs280/proj1/`  
	* here we are making a copy of a repo to work use on CAEN (you can clone anywhere)
	* `git` will most likely warn you that you've cloned an empty repo
5. close CAEN and go back to your local machine. (optional if you only work on CAEN)
6. make sure you have git installed  
	* `git --version` will give you a version number if you do
	* if you don't, [go here](http://git-scm.com/)
6. clone your new repo to your local machine in a sensible directory  
	`git clone uniqname@login.engin.umich.edu:~/.git/eecs280/proj1`
7. open the new folder and add your project files (or some blank test file)
8. type `git commit -am "initial commit"` to commit your changes
9. then type `git push origin master` to send them to the server
	* you'll only have to type `origin master` once to let your machine know to create the `master` branch on the remote repo
10. log back into CAEN and go to your regular project files (not the ones in `.git`) use `git pull` to pull the changes you made on your local machine.

* it is important to note that you have to `pull` and `push` on your own even if your on CAEN. when you push to CAEN you're pushing to the hidden remote repo in `.git/` not to your regular file.


### *now you're setup!*

one of the best reasons to use `git` is for the ability to create branches of your code and revert to old versions if you make a mistake - more on this later! (or serach "git tutorial" on google)

## git glossary
* `repo` or `repository`: where `git` stores your files, really just a folder.
* `git clone`: the process of copying a repo, locally or to a different machine
* `git add`: add changes to the stage of next commit
* `git commit`: add changes to your project. each snapshot is a called a `commit`
* `git commit -am "[message]"`: shorthand to add all changes and commit with a message
* `git pull`: pull changes from a repo (used after you've run `clone`)
* `git push`: push changes to a repo
