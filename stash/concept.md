- The git stash command takes your uncommitted changes (both staged and unstaged),
saves them away for later use, and then remove them from your working copy
- But git stash command does not save untracked or ignored files.
  To save untracked files use -u
  `git stash -u`
  To save untracked as well as ignored files use -a(-all)
  `git stash -a`



- to reapply your changes
  `git stash pop`
  popping remove changes from stash and apply it to you working directory
  `git stash apply`
  apply, apply changes to working copy and keep the changes in stash as well, This
  is useful if you want to apply the same stashed changes to multiple branches.



- Multiple stashes
	1. you can run git stash several times to create multiple stashes, and then use git stash list to view them

		```
		D:\MyWorkingDir\how_to_use_github\stash>git stash save "saving third stash and concept.txt"
		Saved working directory and index state On master: saving third stash and concept.txt

		D:\MyWorkingDir\how_to_use_github\stash>git stash list
		stash@{0}: On master: saving third stash and concept.txt
		stash@{1}: WIP on master: cd6eff9 git stash
		stash@{2}: WIP on master: cd6eff9 git stash
		stash@{3}: WIP on master: d455344 Merge branch 'master' of https://github.com/yogitaupadhyay/how_to_use_github into master
		```
	2. git stash pop will re-apply the most recently created stash: `stash@{0}`
	
	3. You can choose which stash to re-apply by passing its identifier as  the last argument, for example:
		`git stash pop stash@{2}`
		
- Partial stash 
	You can also choose to stash just a single file, a collection of files, or individual changes from within files. If you pass the -p option (or --patch) to git stash, it will iterate through each changed "hunk" in your working copy and ask whether you wish to stash it:
	`git stash -p`
	
- Stash branch
If the changes on your branch diverge from the changes in your stash, you may run into conflicts when popping or applying your stash. Instead, you can use git stash branch to create a new branch to apply your stashed changes to:
	
	`git stash barch newBranchName stash@{1}`
	
- Cleaning stash
     clear particular stash
		`git stash drop stash@{1}`
	 clear all stashes 
		`git stash clear`
