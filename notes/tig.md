---
title: tig
created: '2021-05-12T19:12:35.991Z'
modified: '2021-05-12T19:36:29.575Z'
---

# tig

> `tig` - text-mode interface for Git

## install

`brew install tig`

## usage

```sh
tig

git show | tig

tig show --pretty=fuller

tig status
tig BRANCH 	            # show a branch
tig FILE 	              # show history of file
tig blame FILE

tig BRANCHA..BRANCHB        # show difference between two branches
tig TAG:FILE       # show contents of file in a specific revision
tig -C /repo/path       # run in dir /repo/path like `git -C`
```

## shortcuts

```sh
m         # switch to main view
d         # switch to diff view
l         # switch to log view
p         # switch to pager view
t         # switch to (directory) tree view
f         # switch to (file) blob view
g         # switch to grep view
b         # switch to blame view
r         # switch to refs view
y         # switch to stash view
h         # switch to help view
s         # switch to status view
c         # switch to stage view

# all views
j         # move up
k         # move down
U         # move page up         
D         # move page down

J K       # Next/previous
<         # Back
R         # Refresh
q         # Close
Q         # Close all
^N        # Next on parent view
^P        # Previous on parent view

# m - Main view
D         # Toggle date display modes
A         # Toggle author display modes
X         # Toggle commit sha
C         # Cherry pick a commit

# s - Status view
u         # Stage/unstage file or chunk
!         # Revert file or chunk
C         # Commit
M         # Merge
1         # stage line
[         # increase diff context
]         # decrease diff context
```

## see also

- [[git]]
- [devhints.io/tig](https://devhints.io/tig)
- [jonas.github.io/tig/doc/manual](https://jonas.github.io/tig/doc/manual.html)
