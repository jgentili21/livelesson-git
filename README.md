# Git Notes

## Working with git locally

- `git init` : initialize current folder as a git repositoy
- `git clone <URL>` : brings the gir repo from <URL> to current folder
- `git status` :tells us that we need to know about our repo

- `git add <FILE>` : adds <FILE> to the staging area
- `git commit`: open a text editor to write commit message
	- `git commit -m "Message"` : writes Message as a commit without a text editor
- `git log` : shows the log (history) of our commits
	- `git log --oneline` : shows the shorter oneline commit 

- `git diff` : compare current uncomiited state with last known git state
	- `git diff --staged`: runs git diff between the staging area and last known state
- `git diff HEAD~<NUMBER>` : compates HEAD with commit <NUMBER> ago (Realative
- `git diff <HASH>` : compares HEAD with the commit in <HASH>

- `git restore --soure <HASH OR HEAD~> <FILE>`: restore file to <HASH OR ~HEAD~>
	- `git checkout <HASH OR HEAD~> <FILE>`: restores file to <HASH OR HEAD~>
		-`git checkout <HASH OR HEAD~>`: if you forget the file, you end up in detached head
		-`git checkout main` : go back to main
		-`git swich main`L go nack to main

## Working with remotes

- `git remote add <NAME> <URL>` : adds the <URL> as a remote with the name <NAME>
	-<NAME> is by convention called `origin`
- `git remote rm <NAME>`: removes the remote called <NAME>
- `git remote -v` : look at all the remotes you have
- `git push <WHERE> <WHAT>` : pushes the <WHAT> branch to <WHERE>
	-`git push origin main`
- `git pull <WHERE> <WHAT>` : pulls the <WHAT> branch in <WHERE> to our local computer

## Branches

- `git branch <NAME>`: create branch <NAME> where you are (HEAD)
- `git switch <NAME>`: move to the breanch <NAME>
	-`git checkout <NAME>`: also move to the branch <NAME>
- `git switch -c <NAME>`: create and move to the branch <NAME> in 1 command
	- `git checkout -b <NAME>`: also create and move to branch <NAME> in 1 command

- `git merge <BRANCH>`: merge <BRANCH> into your current branch
- `git rebase`: command to change the history of a commit
	- Commits from `git merge` can be automatically combined
- `git rebase <BRANCH>`: incorporate changes from <BRANCH> into current branch
	-`git status`: is your friend
	-`git add <FILE>`: to mark conflic resolution
	-`git rebase --continue`:  move to next commit in rebase
	-`git rebase --abort`: undo git rebase step
- `git rebase -i <COMMIT>`: `HEAD~` or <HASH> of commit to go into interactive rebase
	- you can make multiple commit changes her, e.g., `squash`/`s`
	- `git rebase -i <HASH>^`: use ^ to include that commit in interactive rebase	
- `git stash` or `git commit`: to save work before moving branches
	- `stash` is temporary
	- `git stash list` : see your stashed commits
	- `git stash apply` : apply your last stashed commit
	- `git stash clear` : clean up your stashes

- A `merge` on the remote is called a "pull request" or "merge request"
	- `git push <WHERE> <WHAT>`
	- To update a PR, we make changes to the brancg locally and re-`push`

- A merge conflict can happen after a PR is issued
- `git fetch`: update your git log without making any changes to your files
	- `git fetch --prune`: update your log and also remove deleted remote branches

- `git push -f <WHERE> <WHAT> `: force push to the remote <WHERE> the branch <WHAT>
	- `git push --force-with-lease <WHERE> <WHAT>`: more mindful of collaborators

## Collaborators

- Second person to push, needs to sync the history
- Add collaborators in repository settings
- collaborators will then `git clone <URL>` to get repo on their computer 	
- Each persons branch changes are independent from one another
- Feature branches wont show conflicts until one of them is merged first
- In the settings you can setup branch protection rules to prevent direct changes

## Git Workflows

- Adding a collaborator
- Branching workflow
- Git Flow: a special type of branching workflow
- Forking: is commonly used in open source projects
	- Fork: copy the original remote repo into your account
	- `origin` : is your own remote copy
	- `upstream` : is the original copy
	- Follow branching workflowo
 
