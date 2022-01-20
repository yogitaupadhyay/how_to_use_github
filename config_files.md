## 1. System level config file [--system]
Location: `[path]/etc/gitconfig`

To make changes in this file you need to pass --system flag to git config command.

## 2. User level config file [--global]
Location: `~/.gitconfig or ~/.config/git/config`

Exmaple of user level git config file- 

```
gitconfig file content
_____________________________________


[user]
	name = abc
	email = abc@gmail.com
[core]
	compression = 0
[http]
	postBuffer = 1048576005
	maxRequestBuffer = 103M
  
  ```
  
To make changes in this file you need to pass --global flag to git config command e.g. 

``
$ git config --global user.name "abc"
``

  ## 3. Repo level config file [--local]
 Location: `.git/config`
  Exmaple of repo level git config file-
  
 
  
  ```
  [core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "java8"]
	url = https://github.com/yogitaupadhyay/java8
	fetch = +refs/heads/*:refs/remotes/java8/*
[branch "master"]
	remote = java8
	merge = refs/heads/master

  
  ```
   To make changes in this file you need to pass --local flag to git config command. This is also default flag with config command. 
  
  ## List all your config files
  ```
  $ git config --list --show-origin`
	file:C:/Program Files/Git/etc/gitconfig diff.astextplain.textconv=astextplain
	file:C:/Program Files/Git/etc/gitconfig filter.lfs.clean=git-lfs clean -- %f
	file:C:/Program Files/Git/etc/gitconfig filter.lfs.smudge=git-lfs smudge -- %f
	file:C:/Program Files/Git/etc/gitconfig filter.lfs.process=git-lfs filter-process
	file:C:/Program Files/Git/etc/gitconfig filter.lfs.required=true
	file:C:/Program Files/Git/etc/gitconfig http.sslbackend=openssl
	file:C:/Program Files/Git/etc/gitconfig http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
	file:C:/Program Files/Git/etc/gitconfig core.autocrlf=true
	file:C:/Program Files/Git/etc/gitconfig core.fscache=true
	file:C:/Program Files/Git/etc/gitconfig core.symlinks=false
	file:C:/Program Files/Git/etc/gitconfig core.editor="C:\\Program Files\\Notepad++\\notepad++.exe" -multiInst -notabbar -nosession -noPlugin
	file:C:/Program Files/Git/etc/gitconfig pull.rebase=false
	file:C:/Program Files/Git/etc/gitconfig credential.helper=manager
	file:C:/Users/abc/.gitconfig user.email=abc@gmail.com
	file:C:/Users/abc/.gitconfig user.name=abc
```


## Your identity setup
```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

## Your default editor

```
$ git config --global core.editor vim

```
If not configured, Git uses your system’s default editor.

We can check above from result of `git config --list --show-origin`, default editor is notepad++
`file:C:/Program Files/Git/etc/gitconfig core.editor="C:\\Program Files\\Notepad++\\notepad++.exe" -multiInst -notabbar -nosession -noPlugin`
On a Windows system, if you want to use a different text editor, you must specify the full path to its
executable file. This can be different depending on how your editor is packaged.

## Your default branch name
`$ git config --global init.defaultBranch main`
By default, defualt branch name is master

## Get all config values

```
yogita@LAPTOP-C9MC4OMS MINGW64 ~
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
core.editor="C:\\Program Files\\Notepad++\\notepad++.exe" -multiInst -notabbar -nosession -noPlugin
pull.rebase=false
credential.helper=manager
user.email=abc@gmail.com
user.name=abc
init.defaultbranch=main
```

## Get particular config value
```
$ git config user.name
 abc
$ git config core.editor
 "C:\\Program Files\\Notepad++\\notepad++.exe" -multiInst -notabbar -nosession -noPlugin

```

## Find put from which config file does the config value is actually used

```
$ git config --show-origin pull.rebase
file:C:/Program Files/Git/etc/gitconfig false

```

## Help manual

```
$ git help <verb>
$ git <verb> --help
$ man git-<verb>
``
e.g.
`git help config`- this will open a config  command help page
