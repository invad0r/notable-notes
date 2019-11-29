---
tags: [git]
title: git
created: '2019-07-30T06:19:49.063Z'
modified: '2019-09-05T06:24:52.400Z'
---

# git

### test remote ssh connection
```sh
ssh -Tv git@example.com       # test-ssh-connection
```


### day-to-day
```sh
git diff [file]           # Show changes between working directory and staging area.

git diff --staged [file]  # Shows changes in the staging area that haven't been commited.

git checkout -- [file]    # Discard changes in working directory. This operation is unrecoverable !

git add [file]            # Add a file to the staging area. Use . instead of full file path, to add all changes files from current directory down into directory tree.


git reset [file]          # Get file back from staging area to working directory.

git reset HEAD -- FILE    # undo git add FILE


git add --patch file      # add specific lines to commit


git diff HEAD@{1} .env    # diff wir previouse version
```

### reverting changes
```sh
git reset [--hard] [target reference]   # Switch current branch to the  target reference, and leaves a ifference as anuncommited changes. When --hard is used, all changes are discarded.

git revert [commit sha]   # Create a new commit, reverting changes from the speci fied commit. Itgenerates n inversion of changes.
```

[Git tips and tricks | GitLab](https://about.gitlab.com/2016/12/08/git-tips-and-tricks/)

### restore deleted file
```sh
git log --diff-filter=D --summary | grep delete | grep filename   # find deleted file

git log --all -- path/file.sh             # get hash to file; exec from git-root-dir !!

git checkout e7s..37^ --  path/file.sh    # note ^ after SHA !
```

### search for file in history
```sh
git rev-list --all registrator.go \
  | ( while read revision; do git grep -F 'swarm' $revision registrator.go done )
```
## see also
- [[git config]]
- [[ssh]]
- [[gitlab api]]
- [search for string in a single files history - Stack Overflow](https://stackoverflow.com/a/10223136)
