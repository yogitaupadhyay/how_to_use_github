## Skipping the staging area

staging area, Git provides a simple shortcut. Adding the -a option to the git commit command makes
Git automatically stage every file that is already tracked before doing the commit, letting you skip
the git add part:

`git commit -a`

## Remove files

🌀 ```rm modeified_file.txt```\
It will simply remove the tracked but not staged file and you will see it as deleted file under "Changes not staged for commit:"(Tracked but not staged)



🌀 ```git rm modeified_file.txt```

It will simply remove  the tracked but not staged file and you will see it under "`Changes to be committed:"(staged)


🌀 `git rm stagedFile.txt -f`\
  Remove From staging area 
 
🌀 `git rm stagedFile.txt --cached`\
  Remove From staging area but keep it in th system as untracked file (Staging area --> Untracked file)

```

D:\MyWorkingDir\LowLevelDesign>git rm stagedFile.txt --cached
rm 'stagedFile.txt'

D:\MyWorkingDir\LowLevelDesign>git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    stagedFile.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   modeified_file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        stagedFile.txt
```
## Renaming files
`git mv modeified_file.txt modified.txt` 



```
D:\MyWorkingDir\LowLevelDesign>git mv modeified_file.txt modified.txt

D:\MyWorkingDir\LowLevelDesign>git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    modeified_file.txt -> modified.txt
        modified:   stagedFile.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   modified.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
```
this is actually equivalent to 

```
$ mv README.md README
$ git rm README.md
$ git add README```
