Tags are to tag specific points in a repository’s history as being important.

Git supports two types of tags: \
🌀 lightweight:
   A lightweight tag is very much like a branch that doesn’t change — it’s just a pointer to a specific commit.\

🌀 annotated:
    Annotated tags are stored as full objects in the Git database. They’re checksummed;
    contain the tagger name, email, and date; have a tagging message; and can be signed and verified
    with GNU Privacy Guard (GPG). \
    
 ## Creating tags
 Simple `git tag<tagName>` or Annotated `git tag -a <tag-name> -m <messgae name>`
 
  ```
 D:\MyWorkingDir\LowLevelDesign>git tag list

D:\MyWorkingDir\LowLevelDesign>git tag  -a gitCommandTest -m  "this commit is to test some git commands"

D:\MyWorkingDir\LowLevelDesign>git tag
gitCommandTest
list

```

## Creating tag ons specific commit

```
D:\MyWorkingDir\LowLevelDesign>git log --oneline
1d2e80d (HEAD -> master, tag: list, tag: gitCommandTest, origin/master) Adding commit, just to verify some of the git commands
2fa2af7 bridge
149322d adding decorator design pattern

D:\MyWorkingDir\LowLevelDesign>git tag -a "addingBridge" -m "this is imp" 2fa2af7

D:\MyWorkingDir\LowLevelDesign>git tag
addingBridge
gitCommandTest
list
```

## Check all your tags
```
git tag
git tag --list


D:\MyWorkingDir\LowLevelDesign>git tag
gitCommandTest
list

D:\MyWorkingDir\LowLevelDesign>git tag -l "git*"
gitCommandTest
```

```

D:\MyWorkingDir\LowLevelDesign>git show gitCommandTest
tag gitCommandTest
Tagger: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Sun Jan 23 12:58:19 2022 +0530

this commit is to test some git commands

commit 1d2e80df6dd8ed066b26d693566ffc22525b325d (HEAD -> master, tag: list, tag: gitCommandTest, origin/master)
Author: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Sat Jan 22 12:40:52 2022 +0530

    Adding commit, just to verify some of the git commands

diff --git a/modified.txt b/modified.txt
new file mode 100644
index 0000000..f6a6b18
--- /dev/null
+++ b/modified.txt
@@ -0,0 +1 @@
+Hello this is modified file
\ No newline at end of file
diff --git a/stagedFile.txt b/stagedFile.txt
new file mode 100644
index 0000000..c238a23
--- /dev/null
+++ b/stagedFile.txt
@@ -0,0 +1 @@
+hello this is staged file, modified again
\ No newline at end of file

D:\MyWorkingDir\LowLevelDesign>

```
## Push all tags

```
D:\MyWorkingDir\LowLevelDesign>git push origin --tags
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 168 bytes | 168.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/yogitaupadhyay/LowLevelDesign
 * [new tag]         addingBridge -> addingBridge
 * [new tag]         list -> list

```
## Push only annotated
```
git push <remote> --follow-tags
```

## Deleting tag from server

```

D:\MyWorkingDir\LowLevelDesign>git push origin :refs/tags/list
To https://github.com/yogitaupadhyay/LowLevelDesign
 - [deleted]         list
 
 ```
 
```
D:\MyWorkingDir\LowLevelDesign>git push origin --delete addingBridge
To https://github.com/yogitaupadhyay/LowLevelDesign
 - [deleted]         addingBridge
 ```
