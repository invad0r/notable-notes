---
tags: [git]
title: git log
created: '2019-08-19T13:29:05.856Z'
modified: '2019-08-20T10:40:25.803Z'
---

# git log

```sh
git log --oneline --graph --decorate    # An overview with references labels and history graph. One commit er line.

git log [-n count]    # List commit history of current branch. -n count limits list to last n commits.

git log ref..         # List commits that are present on current branch and not merged into ref.A ref can be e.g. a branch name or a tag name.

git log ..ref         # List commit, that are present on ref and not merged into current branch.

git reflog            # List operations (like checkouts, commits etc.) made on local repository.

git log --follow -p -- file   # follow file history
```

## review the differences 
> git and have 1 and 1 different commits each, respectively

```sh
git log HEAD..origin/master   # see where origin/master branch has diverged
```

## pretty format
```sh
alias glg='git log \
  --graph \
  --pretty=format:"%Cred%h%Creset \
  -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" \
  --abbrev-commit'
```
[[bash alias]]
