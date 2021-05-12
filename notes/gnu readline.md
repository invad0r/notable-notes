---
tags: [shell]
title: gnu readline
created: '2019-07-30T06:19:49.019Z'
modified: '2021-05-12T08:47:10.236Z'
---

# gnu readline

`bash emacs shortcuts`
## movement
| | |
|--|--|
| <kbd>CTRL+A</kbd>	| move to beginning of line |
| <kbd>CTRL+B</kbd>	| moves backward one character |
| <kbd>CTRL+E</kbd>	| moves to end of line |
| <kbd>CTRL+F</kbd>	| moves forward one character |


| | |
|--|--|
| <kbd>CTRL+C</kbd>	| halts the current command |
| <kbd>CTRL+G</kbd>	| aborts the current editing command and ring the terminal bell |
| <kbd>CTRL+D</kbd>	| deletes one character backward or logs out of current session, similar to exit |
| <kbd>CTRL+U</kbd>	| kills backward from point to the beginning of line |
| <kbd>CTRL+W</kbd>	| kills the word behind the cursor |
| <kbd>CTRL+Y</kbd>	| retrieves (yank) last item killed |
| <kbd>CTRL+J</kbd>	| same as RETURN |
| <kbd>CTRL+K</kbd>	| deletes forward to end of line |
| <kbd>CTRL+L</kbd>	| clears screen and redisplay the line |
| <kbd>CTRL+M</kbd>	| same as RETURN |
| <kbd>CTRL+O</kbd>	| same as RETURN, then displays next line in history file |
| <kbd>CTRL+T</kbd>	| transposes two characters |
| <kbd>CTRL+V</kbd>	| makes the next character typed verbatim |
| <kbd>CTRL+X</kbd>	| lists the possible filename completefions of the current word |
| <kbd>CTRL+Z</kbd>	| stops the current command, resume with fg in the foreground or bg in the background |
| <kbd>CTRL+N</kbd>	| next line in command history |
| <kbd>CTRL+P</kbd>	| previous line in command history |
| <kbd>CTRL+R</kbd>	| searches backward |
| <kbd>CTRL+S</kbd>	| searches forward |

## `~/.inputrc`
> create canned macros by mapping key sequences to input strings

```sh
Control-o: "> output.txt"
Control-j: "\C-a$(\C-e)"    # macro moves to the beginning of the line with Ctrl-A, 
                            # adds `$(` then moves to the end of the line with Ctrl-E and adds `)`
```

## see also
- [[bash bind]]
- [Is there a way to make alt-f and alt-b jump word forward on Mac? - Stack Overflow](https://stackoverflow.com/questions/20146972/is-there-a-way-to-make-alt-f-and-alt-b-jump-word-forward-and-backward-instead-of)
- [readline - twobithistory.org](https://twobithistory.org/2019/08/22/readline.html)
