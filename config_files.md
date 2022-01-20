## 1. System level config file 
`[path]/etc/gitconfig`

## 2. User level config file
`~/.gitconfig or ~/.config/git/config`

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
  ## 3. Repo level config file
  `.git/config`
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
  
  
  
