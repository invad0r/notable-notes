---
deleted: true
tags: [git]
title: git config
created: '2019-08-19T13:27:55.795Z'
modified: '2019-08-19T13:28:34.328Z'
---

# git config

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
