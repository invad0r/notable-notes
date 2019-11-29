---
tags: [vim]
title: vim splits
created: '2019-07-30T06:19:49.261Z'
modified: '2019-08-26T06:59:49.304Z'
---

# vim splits

```sh
:vsp    # vertical split
:sp     # horizontal split
```

<kbd>C-w j</kbd> -  navigate down
<kbd>C-w k</kbd> -  navigate up
<kbd>C-w l</kbd> -  navigate right
<kbd>C-w h</kbd> -  navigate left
<kbd>C-w _</kbd> -  Max out the height of the current split
<kbd>C-w |</kbd> -  Max out the width of the current split
<kbd>C-w =</kbd> -  Normalize all split sizes, which is very handy when resizing terminal


## resize
```sh
:res
:resize 60		" resize splits e.g. :help
:resize +5 

:vertical resize 80
:vertical resize +4
```
