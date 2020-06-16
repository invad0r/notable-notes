---
tags: [vim]
title: vim command mode
created: '2019-09-05T11:15:25.126Z'
modified: '2020-04-23T09:38:14.830Z'
---

# vim command mode

## usage

```vim
:h                        ; get help
:help vim-modes           ; display help to vim-modes


:set list                 ; show non printable characters
:digraphs                 ; list special characters

:verbose set filtetype?   ; get value of filetype
:scriptnames

:w                        ; write
:w !sudo tee %            ; write with sudo permission
:wq                       ; write and quit
:x  

:n
:prev
:args                     ; show open files

:syntax on                ; syntax highlighting
:sy on
:syntax of
:sy off
:colorscheme <colorscheme>
:colo delek               ; on osx check avail colorschemes here: /usr/share/vim/vim80/colors


:ls                   ; list buffers
:ls!                  ; list deleted buffers

:e file               ; edit, adds file to buffer
:e#                   ; open prevous file
:e#3                  ; open 3rd last file in buffer

:b buffer-filename    ; opens from deleted buffer

:bn                   ; buffer next
:bp                   ; buffer previous

:bd                   ; buffer delete
:bd 4                 ; close buffer with id 4

:bw                   ; buffer wipe / delete all buffers


:tabnew filename		  ; load file in new tab
:tabm n
:tabm 2		            ; move current tab to position 2
:Sexplore
:Sex                  ; SplitExplore
:Vex                  ; VerticalExplore
:Tex                  ; TabExplore    <=== *** this is the one ***
:Ex


:10,100s/^/#/         ; substitute (that reads, from line 10 to 100 substitute line start (^) with a # sign.)

:1, 21 j              ; join line 1 to 21

:%s/\n/ /g            ; substitute line break with space


:r
:read
		name		"insert file content below curser
		!cmd		"insert cmd content below curser

:r!date     # insert date


:reg
:register
:di
:display

:pu
:put
:[line]pu[t] [x]	" put text from register x
:[line]pu[t]! [x]	" put text from register x
```

## see also
- [[vim set]]
- [[vim]]
- [[vim visual mode]]
