---
tags: [git]
title: git branch
created: '2019-08-16T06:03:00.514Z'
modified: '2019-12-04T15:03:39.042Z'
---

# git branch

> git branch 

## usage
```sh
git branch -l    # list local branches

git branch -r    # list remote 

git branch -a    # list all: local and remote   

git branch -v     # verbose

git branch -vv    # more verbose e.g. show gone branches `[origin/refactoring: gone]`


git branch branchName       # Create new branch, referencing the current HEAD

git checkout [-b] [name]    # Switch working directory  to the specified branch. With -b: Git will create he specified branch if it does not exist

git merge [from name]       # Join specified [from name] branch into your current branch (the one you are on currenlty).

git branch -d [name]        # Remove selected branch, if it is already merged into any other. -D  instead of -d  forces deletion.
```

## see also
-
