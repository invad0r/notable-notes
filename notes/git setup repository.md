---
tags: [git]
title: git setup repository
created: '2019-08-19T13:42:28.415Z'
modified: '2019-08-23T09:46:18.448Z'
---

# git setup repository

## setup from empty repository
```sh
git clone git@git.domain.net:user/foo.git

git add README.md

git commit -m "add README"

git push -u origin master
```

## setup existing folder
```sh
git init

git remote add origin git@git.domain.net:user/foo.git

git add --all

git commit

git push -u origin master

```

## setup existing Git repository
```sh
git remote add origin git@git.domain.net:user/foo.git

git remote set-url origin https://github.com/USERNAME/REPOSITORY.git    # switch remote url fomr ssh to https

git push -u origin --all

git push -u origin --tags
``` 

## see also
- [[git remote]]
