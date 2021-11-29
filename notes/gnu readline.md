---
tags: [shell]
title: gnu readline
created: '2019-07-30T06:19:49.019Z'
modified: '2021-11-05T10:06:19.331Z'
---

# gnu readline

> `bash emacs shortcuts`

## usage

```sh
CTRL + A      # move to beginning of line
CTRL + B      # moves backward one character
CTRL + E      # moves to end of line
CTRL + F      # moves forward one character

CTRL + C      # halts the current command
CTRL + G      # aborts the current editing command and ring the terminal bell
CTRL + D      # deletes one character backward or logs out of current session, similar to exit
CTRL + U      # kills backward from point to the beginning of line
CTRL + W      # kills the word behind the cursor
CTRL + Y      # retrieves (yank) last item killed
CTRL + J      # same as RETURN
CTRL + K      # deletes forward to end of line
CTRL + L      # clears screen and redisplay the line
CTRL + M      # same as RETURN
CTRL + O      # same as RETURN, then displays next line in history file
CTRL + T      # transposes two characters
CTRL + V      # makes the next character typed verbatim
CTRL + X      # lists the possible filename completefions of the current word
CTRL + Z      # stops the current command, resume with fg in the foreground or bg in the background
CTRL + N      # next line in command history
CTRL + P      # previous line in command history
CTRL + R      # searches backward
CTRL + S      # searches forward


# create canned macros by mapping key sequences to input strings
cat <<EOT > ~/.inputrc
Control-o: "> output.txt"
Control-j: "\C-a$(\C-e)"    # macro moves to the beginning of the line with Ctrl-A, 
                            # adds `$(` then moves to the end of the line with Ctrl-E and adds `)`
EOT
```

## see also
- [[bash bind]]
- [Is there a way to make alt-f and alt-b jump word forward on Mac? - Stack Overflow](https://stackoverflow.com/questions/20146972/is-there-a-way-to-make-alt-f-and-alt-b-jump-word-forward-and-backward-instead-of)
- [readline - twobithistory.org](https://twobithistory.org/2019/08/22/readline.html)
