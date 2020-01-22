---
tags: [vim]
title: vim command mode
created: '2019-09-05T11:15:25.126Z'
modified: '2020-01-22T09:25:14.693Z'
---

# vim command mode

## usage

```vim
:h                  ;get help
:help
		vim-modes
```

```vim
:set

:verbose set filtetype?   #get value of filetype
:scriptnames

:w              # write
:w !sudo tee %  # write with sudo permission


:e file       # edit file
:wq           # write and quit
:x  

:digraphs     # list special characters

:n
:prev
:args       # show open files
```

## syntax highlighting
```vim
:syntax on
:sy on

:syntax of
:sy off

:colorscheme <colorscheme>
:colo delek
# on osx check avail colorschemes here: /usr/share/vim/vim80/colors
```

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


```vi
:10,100s/^/#/      ; substitute (that reads, from line 10 to 100 substitute line start (^) with a # sign.)

:1, 21 j           ; join line 1 to 21

:%s/\n/ /g         ; subst line break with space
```

## see also
- [[vim set]]
- [[vim]]
- [[vim visual mode]]
