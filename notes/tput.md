---
tags: [linux]
title: tput
created: '2019-07-30T06:19:49.254Z'
modified: '2020-04-15T06:28:06.137Z'
---

# tput

> initialize a terminal or query terminfo database

## usage
```sh
tput longname     # prints term longname  e.g. "VT 100/ANSI X3.64 virtual terminal"

tput cup 5 20     # move the cursor to the position 20 characters to the right and 5 rows down


# capabilitie       Description
#  longname         Full name of the terminal type
#  lines            Number of lines in the terminal
#  cols             Number of columns in the terminal
#  colors           Number of colors available
#  sc 	            Save the cursor position
#  rc 	            Restore the cursor position
#  home             Move the cursor to upper left corner (0,0)
#  cup ROW COL   	  Move the cursor to position row, col
#  cud1 	          Move the cursor down 1 line
#  cuu1 	          Move the cursor up 1 line
#  civis 	          Set to cursor to be invisible
#  cnorm 	          Set the cursor to its normal state
   
# val  color
#  0 	 black
#  1 	 red
#  2 	 green
#  3 	 yellow
#  4 	 blue
#  5 	 magenta
#  6 	 cyan
#  7 	 white
#  8 	 not used
#  9 	 reset to default color
```

## see also
- [[diff]]
- [[infocmp]]
- [LinuxCommand.org: tput](http://linuxcommand.org/lc3_adv_tput.php)
