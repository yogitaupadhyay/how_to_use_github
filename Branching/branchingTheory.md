
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
