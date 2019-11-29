---
tags: [vim]
title: vim
created: '2019-07-30T06:19:49.263Z'
modified: '2019-09-05T11:17:47.510Z'
---

# vim

## open file
```sh
vim -p file1 file2 file3	# open files in tabs

vim $(!!)		            # open file from last output
```

### multiline-indent

- <kbd>ctrl + v</kbd>  - then move up or down
- <kbd>shift + i</kbd>  - multiline insert
- <kbd>esc</kbd>

[vim - Indent multiple lines quickly in vi - Stack Overflow](http://stackoverflow.com/a/235841/2087704)


### vim file

```sh
# -*- mode: ruby -*-
# vi: set ft=ruby : 

# vim: ft=json
```

## see also
- [[vim command]]
