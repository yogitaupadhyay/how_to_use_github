Note: \
🌀 git clone command implicitly adds the origin remote for you.\

## Find out your remote
`git remote` or `git remote -v` or `git remote show origin`

```
D:\MyWorkingDir\LowLevelDesign>git remote
origin

D:\MyWorkingDir\LowLevelDesign>git remote -v
origin  https://github.com/yogitaupadhyay/LowLevelDesign (fetch)
origin  https://github.com/yogitaupadhyay/LowLevelDesign (push)

D:\MyWorkingDir\LowLevelDesign>git remote show origin
* remote origin
  Fetch URL: https://github.com/yogitaupadhyay/LowLevelDesign
  Push  URL: https://github.com/yogitaupadhyay/LowLevelDesign
  HEAD branch: main
  Remote branches:
    main   tracked
    master tracked
  Local ref configured for 'git push':
    master pushes to master (fast-forwardable)

```
## Add new remote

`git remote add <shortname> <url>`
  
```
D:\MyWorkingDir\LowLevelDesign>git remote add newOrigin https://github.com/yogitaupadhyay/LowLevelDesign

D:\MyWorkingDir\LowLevelDesign>git remote -v
newOrigin       https://github.com/yogitaupadhyay/LowLevelDesign (fetch)
newOrigin       https://github.com/yogitaupadhyay/LowLevelDesign (push)
origin  https://github.com/yogitaupadhyay/LowLevelDesign (fetch)
origin  https://github.com/yogitaupadhyay/LowLevelDesign (push)

D:\MyWorkingDir\LowLevelDesign>git remote
newOrigin
origin
```

## Using shortnames
🌀 You can use your shorname e.g. origin or newOrigin here to fetch or push data e.g. git push origin  or git fetch new origin etc.

```
D:\MyWorkingDir\LowLevelDesign>git fetch newOrigin
From https://github.com/yogitaupadhyay/LowLevelDesign
 * [new branch]      main       -> newOrigin/main
 * [new branch]      master     -> newOrigin/master
```
## Git pull

* If you want the default behavior of git (fast-forward if possible, else create a merge commit): git config --global pull.rebase "false"
* If you want to rebase when pulling: git config --global pull.rebase "true"


## Rename Git remote 

```

D:\MyWorkingDir\LowLevelDesign>git remote rename newOrigin yogi

D:\MyWorkingDir\LowLevelDesign>git remote -v
origin  https://github.com/yogitaupadhyay/LowLevelDesign (fetch)
origin  https://github.com/yogitaupadhyay/LowLevelDesign (push)
yogi    https://github.com/yogitaupadhyay/LowLevelDesign (fetch)
yogi    https://github.com/yogitaupadhyay/LowLevelDesign (push)

```

## Remove git remote 

```

D:\MyWorkingDir\LowLevelDesign>git remote remove yogi

D:\MyWorkingDir\LowLevelDesign>git remote -v
origin  https://github.com/yogitaupadhyay/LowLevelDesign (fetch)
origin  https://github.com/yogitaupadhyay/LowLevelDesign (push)

```

```
D:\MyWorkingDir\LowLevelDesign>git remote rm yogi

D:\MyWorkingDir\LowLevelDesign>git remote
origin
```


