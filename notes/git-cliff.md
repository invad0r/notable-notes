---
tags: [rust]
title: git-cliff
created: '2021-10-08T11:16:16.864Z'
modified: '2023-03-22T10:36:29.677Z'
---

# git-cliff

> generate changelog files from the git history by utilizing conventional commits as well as regex-powered custom parsers

## install

```sh
cargo install git-cliff
```

## usage

```sh
git cliff --init      # create cliff.toml


git cliff
git-cliff --config cliff.toml --repository .
git-cliff --workdir .


git cliff --tag 1.0.0   # set tag for the "unreleased" changes
```

## see also

- [github.com/orhun/git-cliff](https://github.com/orhun/git-cliff)
- [[git]]
- [[cargo]]
- [[git-chglog]]
