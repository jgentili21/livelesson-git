# Git Notes

## Working with git locally

'git init' : initialize current folder as a git repositoy
'git clone <URL>' : brings the gir repo from <URL> to current folder
'git status' :tells us that we need to know about our repo

'git add <FILE>' : adds <FILE> to the staging area
'git commit': open a text editor to write commit message
	- 'git commit -m "Message"' : writes Message as a commit without a text editor
- 'git log' : shows the log (history) of our commits
	- 'git log --oneline' : shows the shorter oneline commit 

- 'git diff' : compare current uncomiited state with last known git state
	- 'git diff --staged': runs git diff between the staging area and last known state
- 'git diff HEAD~<NUMBER>' : compates HEAD with commit <NUMBER> ago (Realative
- 'git diff <HASH>' : compares HEAD with the commit in <HASH>

- 'git restore --soure <HASH OR HEAD~> <FILE>': restore file to <HASH OR ~HEAD~>
	- 'git checkout <HASH OR HEAD~> <FILE>': restores file to <HASH OR HEAD~>
		-'git checkout <HASH OR HEAD~>': if you forget the file, you end up in detached head
		-'git checkout main' : go back to main
		-'git swich main'L go nack to main

## Working with remotes

- 'git remote add <NAME> <URL>' : adds the <URL> as a remote with the name <NAME>
	-<NAME> is by convention called 'origin'
- 'git remote rm <NAME>': removes the remote called <NAME>
- 'git remote -v' : look at all the remotes you have
- 'git push <WHERE> <WHAT>' : pushes the <WHAT> branch to <WHERE>
	-'git push origin main'
- 'git pull <WHERE> <WHAT>' : pulls the <WHAT> branch in <WHERE> to our local computer

## Branches

- 'git branch <NAME>': create branch <NAME> where you are (HEAD)
- 'git switch <NAME>': move to the breanch <NAME>
	-'git checkout <NAME>': also move to the branch <NAME>
- 'git switch -c <NAME>': create and move to the branch <NAME> in 1 command
	- 'git checkout -b <NAME>': also create and move to branch <NAME> in 1 command

- 'git merge <BRANCH>': merge <BRANCH> into your current branch
- 'git rebase': command to change the history of a commit
	- Commits from 'git merge' can be automatically combined
- 'git rebase <BRANCH>': incorporate changes from <BRANCH> into current branch
	-'git status': is your friend
	-'git add <FILE>': to mark conflic resolution
	-'git rebase --continue':  move to next commit in rebase
	-'git rebase --abort': undo git rebase step
- 'git rebase -i <COMMIT>': 'HEAD~' or <HASH> of commit to go into interactive rebase
	- you can make multiple commit changes her, e.g., 'squash'/'s'
	- 'git rebase -i <HASH>^': use ^ to include that commit in interactive rebase	
- 'git stash' or 'git commit': to save work before moving branches
