## Flages used with git log
```
-p              Show the patch introduced with each commit.
--stat          Show statistics for files modified in each commit.
--short         stat Display only the changed/insertions/deletions line from the --stat command.
--name-only     Show the list of files modified after the commit information.
--name-status   Show the list of files affected with added/modified/deleted information as well.
--abbrev-commit Show only the first few characters of the SHA-1 checksum instead of all 40.
--relative-date Display the date in a relative format (for example, “2 weeks ago”) instead of
                using the full date format.
--graph         Display an ASCII graph of the branch and merge history beside the log output.
--pretty        Show commits in an alternate format. Option values include oneline, short,
                full, fuller, and format (where you specify your own format).
--oneline       Shorthand for --pretty=oneline --abbrev-commit used together.
                Limiting

-S              It will take a string and show all commit that include some change in that strin e.g. `git log -S func`
                it will show all changes to func string
-<n>            Show only the last n commits
--since,        Limit the commits to those made after the specified date.
--after
--until,        Limit the commits to those made before the specified date.
--before
--author        Only show commits in which the author entry matches the
                specified string.
--committer     Only show commits in which the committer entry matches the
                specified string.
--grep          Only show commits with a commit message containing the string
                Option Description
--no-merges     Not merge commits
                 
                 
```


## Git log of a file
`git log -- path/to/file`

## Git log with patch
`git log -p`
Shows all the commit history with diff changes

` git log -p -2` 
will show 2 latest logs with patch

## Git log with abbreviated statics (git log with git status result)

`git log --stat`

```
D:\MyWorkingDir\LowLevelDesign>git log --stat
commit 7d3bb3dbcdc5e0cf6128f35f640e972fc411e162 (HEAD -> master)
Author: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Sat Jan 22 12:40:52 2022 +0530

    just adding commit

 modeified_file.txt | 1 +
 stagedFile.txt     | 1 +
 2 files changed, 2 insertions(+)

commit 2fa2af7b821a147405f930b1ca0ffb6e94666b6a (origin/master)
Author: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Sun Jan 16 14:01:14 2022 +0530

    bridge

 .../Adaptors/ClientMediaPlayerAdaptor.py            |  11 +++++++++++
 .../ClientMediaPlayerAdaptor.cpython-39.pyc         | Bin 0 -> 783 bytes
 AdapterDesignPatterns/Driver.py                     |  20 ++++++++++++++++++++

 ```
 ## Git log with formatting
 
 `git log --pretty=oneline`
 The oneline value for this option prints each commit on a single line, which is useful if you’re looking at a lot of commits.
 ```
 D:\MyWorkingDir\LowLevelDesign>git log --pretty=oneline
7d3bb3dbcdc5e0cf6128f35f640e972fc411e162 (HEAD -> master) just adding commit
2fa2af7b821a147405f930b1ca0ffb6e94666b6a (origin/master) bridge
149322dea3578ff87f4f283e52226abbb5acd589 adding decorator design pattern
45702e6a37d4c36742491d5995993bdc5b7dec4c adding links
bd9318e2fd88561daa77c32badd0b18a8c3ec033 adding readme
e9857d78dc36ea81db8c9251a9fc06a5740d4163 Merge branch 'master' of https://github.com/yogitaupadhyay/LowLevelDesign into master
8e62cb33eeb36d67a6511ffe4fc587972effe2ab adding about
e1f341894b9d6113acac839c7c9127bfdd2e7145 Adding readme
30e91f33ab581b952f13ab3db01ed90a16a2190f First commit
```
`git log --pretty=format:"%h - %an, %ar : %s`

```
D:\MyWorkingDir\LowLevelDesign>git log --pretty=format:"%h - %an, %ar : %s
7d3bb3d - yogitaupadhyay, 7 hours ago : just adding commit
2fa2af7 - yogitaupadhyay, 6 days ago : bridge
149322d - yogitaupadhyay, 8 days ago : adding decorator design pattern
45702e6 - yogitaupadhyay, 9 days ago : adding links
bd9318e - yogitaupadhyay, 9 days ago : adding readme
e9857d7 - yogitaupadhyay, 9 days ago : Merge branch 'master' of https://github.com/yogitaupadhyay/LowLevelDesign into master
8e62cb3 - yogitaupadhyay, 9 days ago : adding about
e1f3418 - yogita upadhyay, 9 days ago : Adding readme
30e91f3 - yogitaupadhyay, 9 days ago : First commit
```
Abbreviations used in format of pretty

```
Specifier Description of Output
%H Commit hash
%h Abbreviated commit hash
%T Tree hash
%t Abbreviated tree hash
%P Parent hashes
%p Abbreviated parent hashes
%an Author name
%ae Author email
%ad Author date (format respects the --date=option)
%ar Author date, relative
%cn Committer name
%ce Committer email
%cd Committer date
%cr Committer date, relative
%s Subject
```
`git log --pretty=format:"%h %s" --graph`

```
git log --pretty=format:"%h %s" --graph
* 2d3acf9 Ignore errors from SIGCHLD on trap
* 5e3ee11 Merge branch 'master' of git://github.com/dustin/grit
|\
| * 420eac9 Add method for getting the current branch
* | 30e367c Timeout code and tests
* | 5a09431 Add timeout protection to grit
* | e1193f8 Support for heads with slashes in them
|/
* d6016bc Require time for xmlschema
* 11d191e Merge branch 'defunkt' into local
```

## Time limited git logs
`git log --since=1.days` or `git log --since=2.weeks` or ` git log --since=3.months` or git log --since="2022-01-22" or `git log since="2 years 1 day 3 minutes ago".`
```
D:\MyWorkingDir\LowLevelDesign>git log --since=1.days
commit 7d3bb3dbcdc5e0cf6128f35f640e972fc411e162 (HEAD -> master)
Author: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Sat Jan 22 12:40:52 2022 +0530

    just adding commit
```

```
D:\MyWorkingDir\LowLevelDesign>git log --since="2022-01-22",

D:\MyWorkingDir\LowLevelDesign>git log --since="2022-01-21"
commit 7d3bb3dbcdc5e0cf6128f35f640e972fc411e162 (HEAD -> master)
Author: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Sat Jan 22 12:40:52 2022 +0530

    just adding commit
  ```
    
  ```
D:\MyWorkingDir\LowLevelDesign>git log -S func
commit 2fa2af7b821a147405f930b1ca0ffb6e94666b6a (origin/master)
Author: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Sun Jan 16 14:01:14 2022 +0530

    bridge

commit bd9318e2fd88561daa77c32badd0b18a8c3ec033
Author: yogitaupadhyay <yogitau2008@gmail.com>
Date:   Thu Jan 13 17:57:21 2022 +0530

    adding readme
  ```
    
    
 ## Custom search 
 ```
 git log --pretty="%h - %s" --author='Junio C Hamano' --since="2008-10-01" \
--before="2008-11-01" --no-merges -- t/
```
