---
title: bfg
created: '2020-11-20T23:52:19.801Z'
modified: '2020-11-20T23:57:40.166Z'
---

# bfg

> removes large or troublesome blobs like git-filter-branch does, but faster. And written in Scala


## usage
```sh
bfg --strip-blobs-bigger-than 100M --replace-text banned.txt REPO.git

bfg --delete-files id_{dsa,rsa}  REPO.git        # delete all files named 'id_rsa' or 'id_dsa'

bfg --strip-blobs-bigger-than 50M  REPO.git      # remove all blobs bigger than 50 megabytes

bfg --replace-text passwords.txt  REPO.git       # replace passwords listed in file (prefix lines 'regex:' or 'glob:' if required) with ***REMOVED*** wherever they occur in repository

# remove all folders or files named '.git' - a reserved filename in Git. 
# these often become a problem when migrating to Git from other source-control systems like Mercurial
bfg --delete-folders .git --delete-files .git  --no-blob-protection  REPO.git  
```

## see also
- [[git]]
- [rtyley.github.io/bfg-repo-cleaner/](https://rtyley.github.io/bfg-repo-cleaner/)
