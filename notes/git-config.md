---
tags: [git, heredoc]
title: git-config
created: '2019-08-01T07:03:58.247Z'
modified: '2019-08-02T10:21:08.175Z'
---

# git-config

```sh
cat <<EOF > ~/.gitconfig
[core]
  editor = vim

[includeIf "gitdir:~/gitlab.com/"]
  path = ~/.gitconfig-gitlab

[includeIf "gitdir:~/github.com/"]
  path = ~/.gitconfig-github
EOF
```

```sh
cat <<EOF > ~/.gitconfig-github
[user]
  name = invad0r
  email = invad0r@gmx.net

[push]
  default = simple
EOF
```
