
## How a single commit work.
**Blob:** file snapshots\
**Tree:** Git checksums each subdirectory and stores them as a tree object in the Git repository.\
**Commit**: a commit object that has the metadata and a pointer to the root project tree so it can re-create that snapshot when needed.


![image](https://user-images.githubusercontent.com/35460298/151110367-b137264f-9043-4c4e-a7d2-fcda8f9e96e6.png)

![image](https://user-images.githubusercontent.com/35460298/151110492-6dc8adc1-7643-43cc-bd30-dc06fb0909fd.png)
## Note: Notice parent in the above image 


## Git branch: A branch in Git is simply a lightweight movable pointer to one of these commits.
 * Creating a new branch: simply create a new pointer to the commit object you are currently are.
 * Head: pointer to the local branch, you are currenlt are. this help you find which branch you currently on.basically(pointer to pointer)
 * Because a branch in Git is actually a simple file that contains the 40 character SHA-1 checksum of
    the commit it points to, branches are cheap to create and destroy. Creating a new branch is as quick
    and simple as writing 41 bytes to a file (40 characters and a newline).

## Checking git graph
```
D:\MyWorkingDir\LowLevelDesign>git log --graph --oneline --decorate --all
* 1d2e80d (HEAD -> master, tag: list, tag: gitCommandTest, origin/master) Adding commit, just to verify some of the git commands
* 2fa2af7 (tag: addingBridge) bridge
* 149322d adding decorator design pattern
* 45702e6 adding links
* bd9318e adding readme
*   e9857d7 Merge branch 'master' of https://github.com/yogitaupadhyay/LowLevelDesign into master
|\
| * e1f3418 Adding readme
* | 8e62cb3 adding about
|/
* 30e91f3 First commit
* f76c324 (origin/main) Initial commit
 ```
## Find out all merged branchw w.r.t current branch
` git branch --merge`
## Find out all unmerged branches w.r.t current branch
`git branch --no-merge`

## Find out all merged branchw w.r.t specified branch
` git branch --merge <SpecificbranchName>`
## Find out all unmerged branches w.r.t specified branch
`git branch --no-merge <SpecificbranchName>`

## Change branch name
`$ git branch --move bad-branch-name corrected-branch-name`
This replaces your bad-branch-name with corrected-branch-name, but this change is only local for
now. To let others see the corrected branch on the remote, push it:
`$ git push --set-upstream origin corrected-branch-name`
```
$ git branch --all
* corrected-branch-name
main
remotes/origin/bad-branch-name
remotes/origin/corrected-branch-name
remotes/origin/main
```
Notice that you’re on the branch corrected-branch-name and it’s available on the remote. However,
the branch with the bad name is also still present there but you can delete it by executing the
following command:
`$ git push origin --delete bad-branch-name`

```
“origin” is not special
Just like the branch name “master” does not have any special meaning in Git,
neither does “origin”. While “master” is the default name for a starting branch
when you run git init which is the only reason it’s widely used, “origin” is the
default name for a remote when you run git clone. If you run git clone -o booyah
instead, then you will have booyah/master as your default remote branch.
86
```
