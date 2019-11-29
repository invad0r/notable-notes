---
tags: [git]
title: git remote
created: '2019-08-23T09:14:38.765Z'
modified: '2019-11-22T08:52:22.606Z'
---

# git remote

## usage
```sh
git remote        # 

git remote -v

git remote show origin


git remote add pb https://github.com/paulboone/ticgit   # add remote

git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
pb	https://github.com/paulboone/ticgit (fetch)
pb	https://github.com/paulboone/ticgit (push)

git fetch pb

git remote rename pb paul     # change a remote’s shortname 

git remote remove paul         # removing remotes


git remote set-url origin https://github.com/USERNAME/REPOSITORY.git    # change remote url ssh -> https

git remote set-url origin git@github.com:USERNAME/REPOSITORY.git        # change remote url https -> ssh
```

## see also
- [[git setup repository]]
- [Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
