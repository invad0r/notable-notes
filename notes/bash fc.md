---
tags: [bash/built-in]
title: bash fc
created: '2019-07-30T06:19:49.048Z'
modified: '2020-01-10T10:17:09.381Z'
---

# bash fc
> `fix command` - open last command from history in editor and run

```sh
fc -l -1000       # list last 1000 command from history


fc -s ls          # execut last command starting with `ls` could be `ls -lah`

alias r='fc -s'   # typing `r cc' runs the last command beginning with `cc' 
                  # and typing `r' re-executes the last command.
```


## running in script 
if you can't source you have to set option and source history !!
```sh
#!/bin/bash
HISTFILE=~/.bash_history   # Or wherever you bash history file lives
set -o history             # enable history
history | grep git
```

## see also
- [[bash history]]
- ["history" stops working when run inside bash script - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/112362/193945)
- [Rapidly invoke an editor to write a long, complex, or tricky command](https://www.commandlinefu.com/commands/view/1446/rapidly-invoke-an-editor-to-write-a-long-complex-or-tricky-command)
