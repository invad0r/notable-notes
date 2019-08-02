---
tags: [vim]
title: vim
created: '2019-07-30T06:19:49.263Z'
modified: '2019-07-30T06:24:37.652Z'
---

# vim

```sh
:verbose set filtetype?   #get value of filetype
:scriptnames

:h
:help
		vim-modes

:digraphs     # list special characters
```


## commands

```sh
:n
:prev
:args       # show open files
```


## syntax highlighting
```sh
:syntax on
:sy on

:syntax of
:sy off

:colorscheme <colorscheme>
:colo delek
# on osx check avail colorschemes here: /usr/share/vim/vim80/colors
```

## register
```sh
:reg
:register
:di
:display

:pu
:put
:[line]pu[t] [x]	" put text from register x
:[line]pu[t]! [x]	" put text from register x
```

```
VISUALMODE !sort
	OBJS = \ 
		backup.o 
		getopt1.o \ 
		getopt.o \ 
		inp.o \ 
		patch.o \ 
		pch.o \ 
		util.o \ 
		version.o \ 
```




### substitute
```vi
:10,100s/^/#/      #(that reads, from line 10 to 100 substitute line start (^) with a # sign.)
```

### open file
```sh
vim -p file1 file2 file3	# open files in tabs

vim $(!!)		            # open file from last output
```



### multiline-indent
```
CTL+v  then move up or down
Shift+i  # multiline insert
ESC
```
[vim - Indent multiple lines quickly in vi - Stack Overflow](http://stackoverflow.com/a/235841/2087704)


### vim file

```sh
# -*- mode: ruby -*-
# vi: set ft=ruby : 

# vim: ft=json
```


### plugins vim-pathogen

- [GitHub - tpope/vim-pathogen: pathogen.vim: manage your runtimepath](https://github.com/tpope/vim-pathogen)
- [GitHub - ekalinin/Dockerfile.vim: Vim syntax file & snippets for Docker's Dockerfile](https://github.com/ekalinin/Dockerfile.vim.git)
- [GitHub - chriskempson/base16-vim: Base16 for Vim](https://github.com/chriskempson/base16-vim.git)
- [GitHub - powerline/fonts: Patched fonts for Powerline users.](https://github.com/powerline/fonts.git)
- [GitHub - vim-airline/vim-airline: lean & mean status/tabline for vim that's light as air](https://github.com/vim-airline/vim-airline)
- [GitHub - airblade/vim-gitgutter: A Vim plugin which shows a git diff in the gutter (sign column) and stages/undoes hunks.](http://github.com/airblade/vim-gitgutter.git)
- [GitHub - fatih/vim-go: Go development plugin for Vim](https://github.com/fatih/vim-go.git)
- [GitHub - elzr/vim-json: A better JSON for Vim: distinct highlighting of keywords vs values, JSON-specific (non-JS) warnings, quote concealing. Pathogen-friendly.](https://github.com/elzr/vim-json.git)
- [GitHub - plasticboy/vim-markdown: Markdown Vim Mode](https://github.com/plasticboy/vim-markdown.git)
- [GitHub - tpope/vim-surround: surround.vim: quoting/parenthesizing made simple](https://github.com/tpope/vim-surround.git)
- [GitHub - hashivim/vim-terraform: basic vim/terraform integration](https://github.com/hashivim/vim-terraform.git)
