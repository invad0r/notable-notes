---
tags: [vcs]
title: git remote
created: '2019-08-23T09:14:38.765Z'
modified: '2020-09-02T17:46:46.109Z'
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

## git setup repository
```sh
# setup from empty repository
git clone git@git.domain.net:user/foo.git
git add README.md
git commit -m "add README"
git push -u origin master

# setup existing folder
git init
git remote add origin git@git.domain.net:user/foo.git
git add --all
git commit
git push -u origin master

# setup existing Git repository
git remote add origin git@git.domain.net:user/foo.git
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git    # switch remote url fomr ssh to https
git push -u origin --all
git push -u origin --tags
``` 

## see also
- [[git setup repository]]
- [Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
