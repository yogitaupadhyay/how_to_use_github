## Status

```
D:\MyWorkingDir\LowLevelDesign>git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .idea/
        .metadata/
        venv/

nothing added to commit but untracked files present (use "git add" to track)
```
```
D:\MyWorkingDir\LowLevelDesign>git status -s
?? .idea/
?? .metadata/
?? venv/

  ```
## Ignoring files

https://github.com/github/gitignore

The rules for the patterns you can put in the .gitignore file are as follows:\
:cyclone: Blank lines or lines starting with # are ignored.\
:cyclone: Standard glob patterns work, and will be applied recursively throughout the entire working
tree.\
:cyclone: You can start patterns with a forward slash (/) to avoid recursivity.\
:cyclone: You can end patterns with a forward slash (/) to specify a directory.\
:cyclone: You can negate a pattern by starting it with an exclamation point (!).
  
  `.gitigonre file`
  ```
    # ignore all .a files
       *.a
       
    # but do track lib.a, even though you're ignoring .a files above
       !lib.a
       
    # only ignore the TODO file in the current directory, not subdir/TODO
       /TODO
       
    # ignore all files in any directory named build
       build/
  
    # ignore doc/notes.txt, but not doc/server/arch.txt
       doc/*.txt
       
    # ignore all .pdf files in the doc/ directory and any of its subdirectories
       doc/**/*.pdf
       

```

## Git Diff

`git diff` - tracked changes which are not yet staged\
`git diff --staged`  or `git diff --cached`- staged changes

## Git difftool
```
D:\MyWorkingDir\LowLevelDesign>git difftool

This message is displayed because 'diff.tool' is not configured.
See 'git difftool --tool-help' or 'git help config' for more details.
'git difftool' will now attempt to use one of the following tools:
kompare emerge vimdiff

Viewing (1/1): 'modeified_file.txt'
Launch 'vimdiff' [Y/n]?
  ```
it will open a tool, show diff in files

## Git commit
`git commit` it will open a editor for you to add commit which contains output of last status command 

```
D:\MyWorkingDir\LowLevelDesign>git commit
hint: Waiting for your editor to close the file...
  
  file
 ___________________________________________________________________ 
  
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Changes to be committed:
#	modified:   stagedFile.txt
#
# Changes not staged for commit:
#	modified:   modeified_file.txt
#
# Untracked files:
#	.gitignore
#


```
`git commit -v` it will open a editor for you to add commit which contains output of last status command + output of last diff command as well

```
D:\MyWorkingDir\LowLevelDesign>git commit -v
hint: Waiting for your editor to close the file...
  
  file
 _____________________________________________________________________________________
  
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Changes to be committed:
#	modified:   stagedFile.txt
#
# Changes not staged for commit:
#	modified:   modeified_file.txt
#
# Untracked files:
#	.gitignore
#
# ------------------------ >8 ------------------------
# Do not modify or remove the line above.
# Everything below it will be ignored.
diff --git a/stagedFile.txt b/stagedFile.txt
index d123ee2..c238a23 100644
--- a/stagedFile.txt
+++ b/stagedFile.txt
@@ -1 +1 @@
-hello this is staged file
\ No newline at end of file
+hello this is staged file, modified again
\ No newline at end of file

```


