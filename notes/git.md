---
tags: [vcs]
title: git
created: '2019-07-30T06:19:49.063Z'
modified: '2021-10-29T12:30:23.993Z'
---

# git

> distributed version-control system for tracking changes in source code during software development.

## config

```sh
git config --global user.name "Your Name"         # Set the name that will be attached to your commits and tags.

git config --global user.email "you@example.com"  # Set the e-mail address that will be attached to your commits and tags.

git config --global color.ui auto                 # Enable some colorization of Git output. 

git config --list [--local|--global]              # list local/global configuration
```

[[.gitconfig]]

## remote

```sh
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

### git setup repository

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

[Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)

## usage
```sh
ssh -Tv git@example.com       # test-ssh-connection

git help CMD
git help -g       # guides
git help GUIDE

git status                # See the status of your work. New, staged, modified files. Current branch.
git status -s             # show short-format output
git status -s | grep -Z "^ D" | awk '{ $1=""; print $0}' | xargs -0 -I% git add -u %    # add deleted files to stage

git ls-files -o --exclude-standard    # show new files


git commit -v     # using $EDITOR
git commit -m "title" -m "message"
git commit -am ..
git commit --allow-empty      # empty commit without changes -> for retriggers !


git show COMMIT           # show changes of commit

git diff FILE             # diff between working directory and staging area
git diff --staged FILE    # diff files in the staging area that haven't been commited
git diff HEAD@{1} .env    # diff wir previouse version

git checkout -- FILE      # discard changes in working directory. This operation is unrecoverable !
git checkout -            # checkout prevous branch
git checkout .            # reset all current changes

git add FILE              # add FILE to the staging area. 
                          # Use `.` instead of full file path, to add all changes files from current directory down into directory tree
git add --patch FILE      # add specific lines to commit


git reset FILE            # Get file back from staging area to working directory.
git reset HEAD -- FILE    # undo git add FILE
git reset --hard HEAD^    # delete last commit

git merge --abort         # cancel merge conflict

git push origin -f


git log --graph --oneline --decorate --color
git log --graph --abbrev-commit --pretty=format:"%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset"
git log -L:<function>:file      # git log of a specific function in a file


git stash       # Put your current changes into stash.
git stash pop   # Apply stored stash content into working directory, and clear stash.
git status      # Clear stash without applying it into working directory
```

## amend

> ammend to already pushed commit

```sh
git add FILE-A FILE-B        # !!! only if nobody has pulled in the mean time !!!

git commit --amend

git push --force-with-lease
```

### reverting changes

```sh
git reset --hard TARGET_REF   # switch current branch to the target reference, and leaves a ifference as anuncommited changes
                              # when --hard is used, all changes are discarded
git revert COMMIT_SHA         # create new commit, reverting changes from the speci fied commit. Itgenerates n inversion of changes
```

### restore deleted file

```sh
git log --diff-filter=D --summary | grep delete | grep filename   # find deleted file
git log --all -- path/file.sh                                     # get hash to file; exec from git-root-dir !!
git checkout e7s..37^ --  path/file.sh                            # note ^ after SHA !
```


### search for file in history

```sh
git rev-list --all registrator.go \
  | ( while read revision; do git grep -F 'swarm' $revision registrator.go done )
```

### pruge file from repository's history

```sh
#   Force Git to process, but not check out, the entire history of every branch and tag
#   Remove the specified file, as well as any empty commits generated as a result
#   Overwrite your existing tags
git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch PATH-TO-YOUR-FILE-WITH-SENSITIVE-DATA" \
  --prune-empty --tag-name-filter cat -- --all
git push origin --force --all       # overwrite repository, as well as all branches you've pushed up
git push origin --force --tags      # remove the sensitive file from your tagged releases
```

## branch

```sh
git branch -l    # list local branches
git branch -r    # list remote 
git branch -a    # list all: local and remote   

git branch -v     # verbose
git branch -vv    # more verbose e.g. show gone branches `[origin/refactoring: gone]`


git branch branchName       # Create new branch, referencing the current HEAD

git checkout -b NAME        # switch working directory to specified branch. 
                            # -b:git will create he specified branch if it does not exist

git merge FROM_NAME         # Join specified [from name] branch into your current branch (the one you are on currenlty).

git branch -d NAME          # Remove selected branch, if it is already merged into any other. -D  instead of -d  forces deletion.
```

## log

```sh
git log [-n count]            # List commit history of current branch. -n count limits list to last n commits.

git log ref..                 # List commits that are present on current branch and not merged into ref.A ref can be e.g. a branch name or a tag name.

git log ..ref                 # List commit, that are present on ref and not merged into current branch.

git reflog                    # List operations (like checkouts, commits etc.) made on local repository.

git log --follow -p -- file   # follow file history


git log HEAD..origin/master   # see where origin/master branch has diverged
                              # "git and have 1 and 1 different commits each, respectively"

git log --oneline --graph --decorate    # An overview with references labels and history graph. One commit er line.

# pretty format
alias glg='git log --graph --pretty=format:"%Cred%h%Creset \
  -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" \
  --abbrev-commit'
```

[[bash alias]]

## tag

```sh
git tag -l                        # list all tags

git tag TAG_NAME COMMIT_SHA       # Create a tag reference named name for current commit. Add commit sha to tag a specific commit instead of current one. 


git tag -a TAG_NAME COMMIT_SHA    # create a tag object named name for current commit
git tag -a TAG_NAME -m "MESSAGE"  # aka annotated tag

# get tag types
# "lightweight" tag is a name in refs/tags that refers to a commit object
# "annotated"   tag is a name in refs/tags that refers to a tag object
git for-each-ref
git for-each-ref refs/tags
# object-hash             object-type   name in refs/tags that refers to the object
# 902fa933e4aa130338b47b8 commit        refs/tags/v1.0-light
# 1f486472cca96a3a7fbd78b tag           refs/tags/v1.1-annot
# fd3cf147ac63122b919a036 commit        refs/tags/v1.2-light

git tag -d TAG_NAME               # remove a tag from a local repository

git push --tags
```

[stackoverflow.com/how-can-i-tell-if-a-given-git-tag-is-annotated-or-lightweight](https://stackoverflow.com/a/40499437/14523221)

## see also

- [[git config]]
- [[ssh]]
- [[bfg]]
- [[gh]]
- [[git-chglog]]
- [gitlab.com/2016/12/08/git-tips-and-tricks](https://about.gitlab.com/2016/12/08/git-tips-and-tricks/)
- [stackoverflow.com/search-for-string-in-a-single-files-history](https://stackoverflow.com/a/10223136)
- [docs.github.com/removing-sensitive-data-from-a-repository](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/removing-sensitive-data-from-a-repository)

