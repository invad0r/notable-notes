---
tags: [vim]
title: vim
created: '2019-07-30T06:19:49.263Z'
modified: '2022-02-15T10:43:27.323Z'
---

# vim

## usage

```sh
vim -p file1 file2 file3	  # open files in tabs

vim $(!!)		                # open file from last output

vim -y                      # easy mode, beavese like click-and-type editore, ctrl+o -> :q to quit
```

[learnbyexample.github.io/mini/vim-prank/](https://learnbyexample.github.io/mini/vim-prank/)

## vim file

```sh
# -*- mode: ruby -*-
# vi: set ft=ruby : 

# vim: ft=json
```

[[vagrant]]

## visual mode

> visual mode permits the user to select the text using the keyboard

```vim
0
A     ; append end of line
a     ; append
D     ; delete
C     ; change

cw    ; correct word
dw    ; delete word

cW    ; correct whole word
dW    ; delete whole word




Ctl+b   ; page backward
Ctl+f   ; page forward

Ctl+d   ; 1/2 page down
Ctl+u   ; 1/2 page up

''      ; move prev curser position

gd             ; goto local declartion
gD             ; goto global declartion
g*             ; goto/jump to next occurrence under cursor
g#             ; goto/jump to prev occurrence under cursor
gt             ; goto next tab
gT             ; goto prev tab
[nnn] gt       ; goto numbered tab


; shares
md    ; marks share `d`
`d    ; navigate to exact position
'd    ; navigate to the line the holds definition

ggVGJ                 ; go to top of file, visually select to end of file and join lines

qqqqqJ@qq@q
; first three q's clear the `q` register
; qqJ@qq records a macro to the `q` register that performs a Join, then calls `q`
; the last `@q` runs it.

ctrl+v j j j j space space shift+i esc multiline-indent
; ctrl + v      then move up or down
; shift + i     multiline insert
; esc

c i w { Ctrl + r " }  wrap word in `{}`
; c i w         Delete the word the cursor is on, and end up in insert mode.
; {             add the first curly-brace
; ctrl + r"     Insert the contents of the `"` register, aka the last yank/delete
; }             add the closing curly-brace 

di'hPl2x  Unquote a word that's enclosed in single quotes
;   di'   Delete the word enclosed by single quotes
;   hP    Move the cursor left one place (on top of the opening quote) and put the just deleted text before the quote
;   l     Move the cursor right one place (on top of the opening quote)
;   2x    Delete the two quotes
```

### marks

> hidden positions, that allow to jump back to specific location or line

```
m{a-zA-Z}     ; lower-case within file, upper-case among all files

`m            ; backtick, jump to exaxt position of mark
'm            ; single quote, jump to beginning of line that holds mark

md            ; mark current position with d
mi            ; mark current position with i

`d            ; navigate to exact position of mark
'i            ; navigate to line that holds defined mark
```

[vim - Indent multiple lines quickly in vi - Stack Overflow](http://stackoverflow.com/a/235841/2087704)
[Moving efficiently - Trammell Hudson's Projects](https://trmm.net/Moving_efficiently)

## command mode

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

## set

set options that configure Vim are of three types:
- `boolean`: on or off (`:help 'autochdir'`)
- `number`: an integer value (`:help 'textwidth'`)
- `string`: a string value (`:help 'backspace'`) 

```sh
:help set

:se[t]              # show options that differ from their default value
                    # show all but terminal options

:set number 	    # Turn line numbers on
:set nonumber 	  # Turn line numbers off
:set invnumber    # Toggle line numbers
:set number!
:set number& 	    # Set option to default value
:set number? 	    # Show value of option

:set syntax=bash


option         short    example               description

shellcmdflag            shellcmdflag=-ic      make Vim’s :! shell behave like your command prompt e.g. for aliases
encoding                encoding=utf-8        

filetype       ft       ft=json
autoindent                          
pastetoggle             pastetoggle=<F3>     
ignorecase                        
list                              
number                            
wrap                              
hlsearch       hls                                 highlight search result (.vimrc)


softtabstop    sts        sts=4
tabstop        ts         ts=2
shiftwidth     sw         sw=8

listchars       lcs       listchars=tab:→\ ,trail:·

listchars=tab:→\ ,trail:·
listchars=tab:>\ ,trail:·,nbsp:.,extends:#
listchars=tab:»\ ,trail:·,nbsp:·,extends:›,precedes:‹,space:.
```

[Vim documentation: options](http://vimdoc.sourceforge.net/htmldoc/options.html#options)
[commands-executed-from-vim-are-not-recognizing-bash .. - stackoverflow.com](https://stackoverflow.com/a/4642855/2087704)

## tabs

```sh
:tabnew filename		  # load file in new tab

:tabm n
:tabm 2		            # move current tab to position 2

gt                    # pext tab
gT                    # prev tab
[nnn] gt              # numbered tab


:Sexplore
:Sex        # SplitExplore

:Vex        # VerticalExplore
:Tex        # TabExplore    <=== *** this is the one ***
:Ex
```

## splits

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


## vim script

```sh
:for i in range(2016,2020)
:  for j in range(1,12)
:    let s = printf("%s-%02d-01;002000,0;00011,111", i, j)
:    put = s
:    endfor
:  endfor
```

```sh
:for i in range(2016,2020)
:  for j in range(1,12)
:    let s = printf("%s-%02d-01;002000,0;00011,111", i, j)
:    put = s
:    endfor
:  endfor
```

## see also

- [[code]]
- [[atom]]
- [[vim command]]
- [tpope/vim-pathogen: pathogen.vim: manage your runtimepath](https://github.com/tpope/vim-pathogen)
- [ekalinin/Dockerfile.vim: Vim syntax file & snippets for Docker's Dockerfile](https://github.com/ekalinin/Dockerfile.vim.git)
- [chriskempson/base16-vim: Base16 for Vim](https://github.com/chriskempson/base16-vim.git)
- [powerline/fonts: Patched fonts for Powerline users.](https://github.com/powerline/fonts.git)
- [vim-airline/vim-airline: lean & mean status/tabline for vim that's light as air](https://github.com/vim-airline/vim-airline)
- [airblade/vim-gitgutter: A Vim plugin which shows a git diff in the gutter...](http://github.com/airblade/vim-gitgutter.git)
- [fatih/vim-go: Go development plugin for Vim](https://github.com/fatih/vim-go.git)
- [elzr/vim-json: A better JSON for Vim:..](https://github.com/elzr/vim-json.git)
- [plasticboy/vim-markdown: Markdown Vim Mode](https://github.com/plasticboy/vim-markdown.git)
- [tpope/vim-surround: surround.vim: quoting/parenthesizing made simple](https://github.com/tpope/vim-surround.git)
- [hashivim/vim-terraform: basic vim/terraform integration](https://github.com/hashivim/vim-terraform.git)
