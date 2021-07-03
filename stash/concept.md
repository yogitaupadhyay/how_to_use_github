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
