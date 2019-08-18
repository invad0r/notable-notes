---
tags: [git]
title: git branch
created: '2019-08-16T06:03:00.514Z'
modified: '2019-08-16T06:06:48.261Z'
---

# git branch

## list branch
```sh
git branch -l    # local branches
git branch -r    # remote 
git branch -a    # all: local and remote   

git branch -v     # verbose
git branch -vv    # more verbose e.g. show gone branches `[origin/refactoring: gone]`
```

## switch branch
```sh
git branch branchName           # Create new branch, referencing the current HEAD

git checkout [-b] [name]    # Switch working directory  to the specified branch. With -b: Git will create he specified branch if it does not exist

git merge [from name]       # Join specified [from name] branch into your current branch (the one you are on currenlty).

git branch -d [name]        # Remove selected branch, if it is already merged into any other. -D  instead of -d  forces deletion.
```


