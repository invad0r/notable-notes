---
tags: [linux, macos]
title: git
created: '2019-07-30T06:19:49.063Z'
modified: '2023-06-01T05:23:12.654Z'
---

# git

> distributed version-control system for tracking changes in source code during software development.

## install

```sh
brew install git
```

## environment

```sh
EDITOR      # see commit
```

## add

```sh
git add FILE              # add FILE to the staging area

git add .                 # add all changes files from current directory down into directory tree

git add --patch FILE      # add specific lines to commit

git add --all "$(git diff --diff-filter=D --name-only)"     # add deleted files, ! watchout for spaces !
```

## alias

```sh
git alias       # list aliases
```

## branch

```sh
-a, --all         # list all branches, local and remote   
-d                # remove selected branch
-D                # forces deletion
-l, --list        # list local branches
-r, --remotes     # list remote 

-v                # verbose
-vv               # more verbose e.g. show gone branches `[origin/refactoring: gone]`
```

```sh
git branch BRANCH_NAME      # create new branch, referencing the current HEAD

git branch -d NAME          # remove selected branch, if it is already merged into any other

git branch --no-merged | xargs git branch -d
```

## checkout

```sh
-b NAME         # will create specified branch if it does not exist

git checkout -- FILE      # discard changes in working directory. Operation is unrecoverable !

git checkout -            # checkout prevous branch

git checkout .            # reset all current changes
```

## clean

```sh
git clean -d -f -x      # remove all files not under source control
```

## commit

```sh
git commit -v     # using $EDITOR
git commit -m "title" -m "message"
git commit -am ..
git commit --allow-empty      # empty commit without changes -> for retriggers !

# amend to already pushed commit
git add FILE-A FILE-B        # !!! only if nobody has pulled in the mean time !!!
git commit --amend
git push --force-with-lease
```

## config

```sh
git config --local --list            # list local configuration
git config --global --list           # list global configuration

git config --global user.name "USER.NAME"         # set name that will be attached to your commits and tags
git config --global user.email "USER@EMAIL"       # set mail that will be attached to your commits and tags
git config --global color.ui auto                 # enable some colorization output
git config --global pull.ff only                  # always override individual pull invocation with "git pull --rebase" or "git pull --no-ff", making it a conscious choice when a fast-forward pull is not possible
git config --global http.sslCert CERT
git config --global http.sslKey KEY
git config --global credential.helper osxkeychain
git config --global credential.helper 'store --file FILE'
git config --global credential.https://HOST USER
```

## .gitconfig

```sh
[alias]
  cpl = !git checkout - && git pull
  cbd = !git checkout -b "update-$(date +%F_%H%M)"

[core]
  editor = vim
  hooksPath = .husky

[init]
  defaultBranch = main

[user]
  name = Some Name
  email = name@mail.com

[remote "origin"]
  gh-resolved = base

[pull]
  ff = only   

[bulkworkspaces]
  WORKSPACE_NAME = PATH
```

```sh
# seperate configs per remote

cat <<EOF > ~/.gitconfig
[includeIf "gitdir:~/gitlab.com/"]
  path = ~/.gitconfig-gitlab

[includeIf "gitdir:~/github.com/"]
  path = ~/.gitconfig-github
EOF

cat <<EOF > ~/.gitconfig-github
[user]
  name  = user
  email = user@mail.com

[push]
  default = simple
EOF
```

## column

```sh
seq 1 100 | git column --mode=column
```

[[column]]


## diff

```sh
git diff FILE             # diff between working directory and staging area
git diff *.txt

git diff --staged FILE    # diff files in the staging area that haven't been commited

git diff HEAD~2 HEAD~1    # diff between the previous commit and the second ancestor commit
git diff HEAD@{1} .env    # diff wir previouse version

git diff --name-only --diff-filter=D | sed 's| |\\ |g' | xargs git add      # add only deleted file to workspace
```

## help

```sh
git help CMD
git help -g       # guides
git help GUIDE
```

## log

```sh
-n COUNT            # limits list to last n commits
```

```sh
git log ref..                 # list commits that are present on current branch and not merged into ref.A ref can be e.g. a branch name or a tag name.

git log ..ref                 # list commit, that are present on ref and not merged into current branch.

git reflog                    # list operations (like checkouts, commits etc.) made on local repository.

git log --follow -p -- file   # follow file history


git log HEAD..origin/master   # see where origin/master branch has diverged
                              # "git and have 1 and 1 different commits each, respectively"

git log --oneline --author="John Smith" 

git log --format="%Cgreen%h%Creset %an"

git log --graph --oneline --decorate --color  # overview with references labels and history graph. One commit er line

git log --graph --abbrev-commit --pretty=format:"%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset"

git log -L:<function>:file      # git log of a specific function in a file

git log --graph \
  --pretty=format:"%Cred%h%Creset \
  -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" \
  --abbrev-commit
```

[[bash alias]]

## ls-files

```sh
git ls-files -o --exclude-standard    # show new files

git ls-files --deleted | xargs -d "\n" git add --all    # add deleted files
git ls-files -z --deleted | xargs -0 git add            # add deleted files
```

## merge

```sh
git merge --abort           # cancel merge conflict

git merge FROM_NAME         # join specified FROM_NAME branch into your current branch
```

## notes

```sh
git notes add -m "this is a test note.."

git notes list

git notes show

git push origin refs/notes/*                    # push notes
git fetch origin refs/notes/*:refs/notes/*      # fetch all notes
```

## remote

```sh
ssh -Tv git@example.com       # test-ssh-connection

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

## reset

```sh
git reset FILE            # Get file back from staging area to working directory

git reset HEAD -- FILE    # undo git add FILE

git reset --hard HEAD^    # delete last commit
```

## rev-list

```sh
# search for file in history
git rev-list --all registrator.go | ( while read revision; do git grep -F 'swarm' $revision registrator.go done )
```

## push

```sh
git push origin -f

git push --set-upstream origin BRANCH_NAME
```

## pull

> fetch from and integrate with another repository or local branch

```sh
git pull

git fetch && git merge # or git rebase
```

## shortlog

> `git-shortlog` - summarize `git log` output

```sh
-n, --numbered    # sort output according to the number of commits per author instead of author alphabetic order
-s, --summary     # suppress commit description and provide a commit count summary only
-e, --email       # show email address of each author

git shortlog -sn                              # rank contributors
git shortlog -sn --grep="^fix" --no-merges    # filter commit message and don't count merge commits
```

## show

```sh
git show COMMIT           # show changes of commit
```

## submodule

```sh
git submodule status                      # list submodules
git submodule status --recursive          # list nested submodules

git submodule update --init --recursive   #


git submodule add https://github.com/chaconinc/DbConnector

git submodule foreach git status
git submodule foreach git pull origin master
```

[git-scm.com/book/en/v2/Git-Tools-Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)

## stash

```sh
git stash       # put current changes into stash

git stash pop   # apply stored stash content into working directory, and clear stash

git status      # clear stash without applying it into working directory
```

## status

```sh
git status                # See the status of your work. New, staged, modified files. Current branch

git status -s             # show short-format output

git status -s | grep -Z "^ D" | awk '{ $1=""; print $0}' | xargs -0 -I% git add -u %    # add deleted files to stage
```

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

---

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

## svn

```sh
# svn to git migraiton
git svn clone \
  --stdlayout \
  --no-metadata \
  --authors-file=FILE \ `# see: svn log --xml`
  svn://HOST/PATH DEST

git svn clone \
  --stdlayout \
  --no-metadata \
  --authors-file=FILE \
  --prefix=origin/ \
  https://repo/svn/PATH/TRUNK  DEST

git svn clone \
  --authors-file=FILE \
  --prefix=origin/ \
  --trunk=PATH/TRUNK \
  https://repo/svn/general \
  DEST
```

[how-to-migrate-svn-repository](http://stackoverflow.com/questions/79165/how-to-migrate-svn-repository-with-history-to-a-new-git-repository)


## see also

- [[ssh]]
- [[bfg]]
- [[git-chglog]]
- [[snv]]
- [[fossil]]
- [[gource]]
- [ohshitgit.com/](https://ohshitgit.com/)
- [git-scm.com/docs](https://git-scm.com/docs)
- [gitlab.com/2016/12/08/git-tips-and-tricks](https://about.gitlab.com/2016/12/08/git-tips-and-tricks/)
- [stackoverflow.com/search-for-string-in-a-single-files-history](https://stackoverflow.com/a/10223136)
- [docs.github.com/removing-sensitive-data-from-a-repository](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/removing-sensitive-data-from-a-repository)

