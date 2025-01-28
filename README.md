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
