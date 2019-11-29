---
tags: [vim]
title: vim command
created: '2019-09-05T11:15:25.126Z'
modified: '2019-09-06T13:16:10.900Z'
---

# vim command

## help

```vim
:h
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

## see also
- [[vim set]]
