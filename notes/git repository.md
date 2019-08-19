---
tags: [git]
title: git repository
created: '2019-08-19T13:42:28.415Z'
modified: '2019-08-19T13:45:09.707Z'
---

# git repository



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

[switching-remote-urls-from-ssh-to-https](https://help.github.com/articles/changing-a-remote-s-url/#switching-remote-urls-from-ssh-to-https)
