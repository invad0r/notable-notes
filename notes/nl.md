---
tags: [linux]
title: nl
created: '2020-08-03T11:54:23.348Z'
modified: '2020-09-02T17:52:01.756Z'
---

# nl

> line numbering filter

## usage
```sh
nl FILE           # print file like cat with line numbers

nl -v 77 FILE     # start with specific line number

# -b OPTION      
#     a     number all lines
#     t     number only nonempty lines
#     n     number no Lines
#     p     number only lines that contain a match for the basic regex

nl -ba FILE   # empty lines get numbered

nl -b p":[0-2]:[0-2]" /etc/passwd     # number lines that match a regex
```

## see also
- [[cat]]
- [[paste]]
- [[wc]]

