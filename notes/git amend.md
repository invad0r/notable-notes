---
tags: [vcs]
title: git amend
created: '2019-08-19T13:27:18.562Z'
modified: '2020-09-02T17:46:46.021Z'
---

# git amend

## usage
```sh
# ammend to already pushed commit
git add FILE-A FILE-B   # !!! only if nobody has pulled in the mean time !!!

git commit --amend

git push --force-with-lease
```

## see also
- 
