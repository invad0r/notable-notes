---
tags: [git]
title: git
created: '2019-07-30T06:19:49.063Z'
modified: '2019-07-30T06:34:05.985Z'
---

# git

### GIT CONFIGURATION
```sh
git config --global user.name "Your Name"         # Set the name that will be attached to your commits and tags.

git config --global user.email "you@example.com"  # Set the e-mail address that will be attached to your commits and tags.

git config --global color.ui auto                 # Enable some colorization of Git output. 

git config --list [--local|--global]              # list local/global configuration
```

### IGNORING FILES
```sh
cat .gitignore

/logs/*             # all files  in logs directory
!logs/.gitkeep      # (excluding the .gitkeep file)
/tmp                # whole tmp directory
*.swp               # all  files *.swp
```

### day-to-day
```sh
git status                # See the status of your work. New, staged, modified files. Current branch.

git diff [file]           # Show changes between working directory and staging area.

git diff --staged [file]  # Shows changes in the staging area that haven't been commited.

git checkout -- [file]    # Discard changes in working directory. This operation is unrecoverable !

git add [file]            # Add a file to the staging area. Use . instead of full file path, to add all changes files from current directory down into directory tree.


git reset [file]          # Get file back from staging area to working directory.

git reset HEAD -- FILE    # undo git add FILE


git commit -m "message"   # Create commit from changes added to the staging area. You can provide -m otherways $EDITOR will be opened.
```

#### add --patch
```sh
git add --patch file

```


### stashing
```sh
git stash       # Put your current changes into stash.

git stash pop   # Apply stored stash content into working directory, and clear stash.

git status      # Clear stash without applying it into working directory
```


### BRANCHING MODEL
```sh
git branch [-l|-r|-a]       # List branches -l: local, -r: remote, -a: local and remote

git branch [name]           # Create new branch, referencing the current HEAD

git checkout [-b] [name]    # Switch working directory  to the specified branch. With -b: Git will create he specified branch if it does not exist

git merge [from name]       # Join specified [from name] branch into your current branch (the one you are on currenlty).

git branch -d [name]        # Remove selected branch, if it is already merged into any other. -D  instead of -d  forces deletion.
```

### log - review work
```sh
git log --oneline --graph --decorate    # An overview with references labels and history graph. One commit er line.

git log [-n count]    # List commit history of current branch. -n count limits list to last n commits.

git log ref..         # List commits that are present on current branch and not merged into ref.A ref can be e.g. a branch name or a tag name.

git log ..ref         # List commit, that are present on ref and not merged into current branch.

git reflog            # List operations (like checkouts, commits etc.) made on local repository.

git log --follow -p -- file   # follow file history
```

### tagging
```sh
git tag                           # List all tags.

git tag [name] [commit sha]       # Create a tag reference named name for current commit. Add commit sha to tag a specific commit instead of current one. 

git tag -a [name] [commit sha]    # Create a tag object named name for current commit. 

git tag -d [name]                 # Remove a tag from a local repository.

git push --tags
```

### reverting changes
```sh
git reset [--hard] [target reference]   # Switch current branch to the  target reference, and leaves a ifference as anuncommited changes. When --hard is used, all changes are discarded.

git revert [commit sha]   # Create a new commit, reverting changes from the speci fied commit. Itgenerates n inversion of changes.
```

### HELP

```sh
git help CMD

git help -g       # guides

git help GUIDE

git diff HEAD@{1} .env    # diff wir previouse version
```
[Git tips and tricks | GitLab](https://about.gitlab.com/2016/12/08/git-tips-and-tricks/)
[switching-remote-urls-from-ssh-to-https](https://help.github.com/articles/changing-a-remote-s-url/#switching-remote-urls-from-ssh-to-https)


### test remote ssh connection
```sh
ssh -Tv git@example.com       # test-ssh-connection
```

## setup repository
```sh
## From empty repository
git clone git@git.domain.net:user/foo.git
git add README.md
git commit -m "add README"
git push -u origin master

## Existing folder
git init
git remote add origin git@git.domain.net:user/foo.git
git add --all
git commit
git push -u origin master

## Existing Git repository
git remote add origin git@git.domain.net:user/foo.git

git remote set-url origin https://github.com/USERNAME/REPOSITORY.git    # switch remote url fomr ssh to https
git push -u origin --all
git push -u origin --tags
``` 


### git restore deleted file
```sh
git log --diff-filter=D --summary | grep delete | grep filename   # find deleted file

git log --all -- path/file.sh             # get hash to file; exec from git-root-dir !!

git checkout e7s..37^ --  path/file.sh    # note ^ after SHA !
```

### ammend to already pushed commit
```sh
git add FILE-A FILE-B   # !!! only if nobody has pulled in the mean time !!!

git commit --amend

git push --force-with-lease
```

### search for file in history
```sh
git rev-list --all registrator.go | ( while read revision; do git grep -F 'swarm' $revision registrator.go done )
```
[Git search for string in a single files history - Stack Overflow](https://stackoverflow.com/a/10223136)
