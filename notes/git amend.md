---
tags: [git]
title: git amend
created: '2019-08-19T13:27:18.562Z'
modified: '2019-08-19T13:27:31.681Z'
---

# git amend

### ammend to already pushed commit
```sh
git add FILE-A FILE-B   # !!! only if nobody has pulled in the mean time !!!

git commit --amend

git push --force-with-lease
```
