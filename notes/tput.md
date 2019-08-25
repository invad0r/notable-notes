---
tags: [linux]
title: tput
created: '2019-07-30T06:19:49.254Z'
modified: '2019-08-20T07:20:01.242Z'
---

# tput

```sh
infocmp     # prints terminal info

infocmp screen
infocmp xterm
```

```sh
tput longname   # prints term longname
# VT 100/ANSI X3.64 virtual terminal

tput cup 5 20    # move the cursor to the position 20 characters to the right and 5 rows down
```

## capabilities
```sh
# Capname        #  Description

  longname        # Full name of the terminal type
  lines           # Number of lines in the terminal
  cols            # Number of columns in the terminal
  colors          # Number of colors available

  sc 	            # Save the cursor position
  rc 	            # Restore the cursor position
  home            # Move the cursor to upper left corner (0,0)
  cup ROW COL   	# Move the cursor to position row, col
  cud1 	          # Move the cursor down 1 line
  cuu1 	          # Move the cursor up 1 line
  civis 	        # Set to cursor to be invisible
  cnorm 	        # Set the cursor to its normal state
   
# Value 	Color

  0 	# Black
  1 	# Red
  2 	# Green
  3 	# Yellow
  4 	# Blue
  5 	# Magenta
  6 	# Cyan
  7 	# White
  8 	# Not used
  9 	# Reset to default color
```
[LinuxCommand.org: tput](http://linuxcommand.org/lc3_adv_tput.php)
