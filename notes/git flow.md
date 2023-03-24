---
tags: [linux, macos]
title: git flow
created: '2021-03-25T08:00:57.686Z'
modified: '2023-03-24T08:25:52.768Z'
---

# git flow

> collection of git extensions providing high-level repository operations for Vincent Driessen's branching model

## isntall

```sh
brew install git-flow
```

## usage

```sh
git flow init -d  # accept all defaults


git flow feature
git flow feature start NAME [BASE]
git flow feature finish NAME

git flow feature publish NAME
git flow feature pull REMOTE NAME

git flow release
git flow release start RELEASE [BASE]
git flow release finish RELEASE

git flow hotfix
git flow hotfix start RELEASE [BASE]
git flow hotfix finish RELEASE

git flow support
git flow support start RELEASE BASE
```

## see also

- [[git]]
- [[git-chglog]]
- [[semtag]]
- [github.com/nvie/gitflow](https://github.com/nvie/gitflow)
- [nvie.com/posts/a-successful-git-branching-model](https://nvie.com/posts/a-successful-git-branching-model/)
