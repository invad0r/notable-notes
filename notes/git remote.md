---
tags: [git]
title: git remote
created: '2019-08-23T09:14:38.765Z'
modified: '2019-08-23T09:46:37.754Z'
---

# git remote

```sh
git remote        # 

git remote -v

git remote show origin
```

## change remote url
git remote set-url command takes two arguments:
- existing remote name. For example, `origin` or `upstream` are two common choices.
- new URL for the remote
```sh
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git    # ssh -> https

git remote set-url origin git@github.com:USERNAME/REPOSITORY.git        # https -> ssh
```

## add remote
```sh
git remote add pb https://github.com/paulboone/ticgit

git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
pb	https://github.com/paulboone/ticgit (fetch)
pb	https://github.com/paulboone/ticgit (push)

git fetch pb
```

## Renaming remotes 
```sh
git remote rename pb paul     # change a remote’s shortname
```

## removing remotes
```sh
git remote remove paul
```

## see also
- [[git setup repository]]
- [Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
