# Git for Collaboration
## Clone a repo
`git clone <repo>`

## Make a feature branch
`git checkout -b <feature>`

## Stage changes
`git add .`

or

`git add <filename>`

## Commit changes
`git commit`  -  I do my initial commit following the guidelines given below

`git commit -m "summary/subject line"` - I do any later commits using this shortcut as I will squash them into the initial commit before pushing to remote

https://chris.beams.io/posts/git-commit/

### Seven rules of a great Git commit message

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

## Keep Feature Branch Up-To-Date with 
Switch to the master branch and do a

`git pull`

Then switch back to your feature branch and do a 

`git rebase master`

This should put all the master changes onto your feature branch and then replay your new commits on top of it assuming that you have no changes left to stage or commit in your feature branch

## Squash Commits

At this point you are ready to push your work out to the remote feature branch.

Ensure that your code is tested and ready to be pushed out and that it is up to date with the master branch.

`git rebase -i HEAD~<number of commits>`

This is an interactive rebase.  Let's break it down into what it does.

`-i` : specifies that it is an interactive rebase

`HEAD~3`: denotes that we want to start from the HEAD of this branch which is the most recent commit, and go back three commits.  We want to rebase all of those into one single commit.

This will open an editor containing a list of all the commits.

`pick 35af6d1 Create README`

`pick bfcb04f New lines`

`pick 22ch002 Fixed typo`

Replace all `pick`s except for the initial one with `squash` then save and exit the editor.
At this point you'll get a second editor that contains all the commit messages.  I usually remove any messages that aren't the initial commit describing the change using proper formatting.  Once you save and exit you're done.


## Push to Remote Branch

`git push`

## Create Pull Request
