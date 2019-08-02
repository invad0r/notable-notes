---
tags: [vim]
title: vim splits
created: '2019-07-30T06:19:49.261Z'
modified: '2019-07-30T06:24:37.671Z'
---

# vim splits

```sh
:vsp    # vertical split
:sp     # horizontal split

C-w j   # navigate down
C-w k   # navigate up
C-w l   # navigate right
C-w h   # navigate left

C-w _   # Max out the height of the current split
C-w |   # Max out the width of the current split
C-w =   # Normalize all split sizes, which is very handy when resizing terminal
```


```sh

# resize
:res
:resize 60		" resize splits e.g. :help
:resize +5 

:vertical resize 80
:vertical resize +4
```
