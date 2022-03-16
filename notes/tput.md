---
tags: [linux]
title: tput
created: '2019-07-30T06:19:49.254Z'
modified: '2022-01-25T12:44:43.476Z'
---

# tput

> initialize a terminal or query terminfo database

## capabilitie

```sh
longname        # Full name of the terminal type
lines           # Number of lines in the terminal
cols            # Number of columns in the terminal
colors          # Number of colors available
sc 	            # ave the cursor position
rc 	            # estore the cursor position
home            # Move the cursor to upper left corner (0,0)
cup ROW COL   	# Move the cursor to position row, col
cud1 	          # ove the cursor down 1 line
cuu1 	          # ove the cursor up 1 line
civis 	        # Set to cursor to be invisible
cnorm 	        # Set the cursor to its normal state

setaf VALUE 	  # set foreground color
setab VALUE 	  # set background color
```

## color

```sh
0 	 # black
1 	 # red
2 	 # green
3 	 # yellow
4 	 # blue
5 	 # magenta
6 	 # cyan
7 	 # white
8 	 # not used
9 	 # reset to default color
```

## usage
```sh
tput cup 0 0      # send sequence to move the cursor to row 0, column 0 (upper left corner of the screen, aka "home" cursor position)
tput cup 5 20     # move the cursor to the position 20 characters to the right and 5 rows down

tput clear        # echo the clear-screen sequence for the current terminal.

tput cols         # print the number of columns for the current terminal.

tput longname     # prints term longname  e.g. "VT 100/ANSI X3.64 virtual terminal"


tput setaf 2; echo '${LBC_VERSION} has been set.'       # print in green
tput setaf 1; echo '${LBC_VERSION} has NOT been set.'   # print in red
```

## see also

- [[diff]]
- [[infocmp]]
- [LinuxCommand.org: tput](http://linuxcommand.org/lc3_adv_tput.php)
