---
tags: [vim]
title: vim buffers
created: '2019-07-30T06:19:49.258Z'
modified: '2019-07-30T06:24:37.662Z'
---

# vim buffers

### list buffers
```sh
:ls         # list buffers
:ls!        # list deleted buffers
```

### edit
```sh
:e test.yml           # adds file to buffer
:e#                   # open prevous file
:e#3                  # open 3rd last file in buffer
```


```sh
:b buffer-filename    # opens from deleted buffer

:bn         # buffer next
:bp         # buffer previous

:bd         # buffer delete
:bd 4       # close buffer with id 4

:bw         # buffer wipe / delete all buffers
```
