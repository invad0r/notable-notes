---
tags: [linux, macos]
title: mkfifo
created: '2021-06-16T15:59:45.047Z'
modified: '2023-03-24T09:50:28.292Z'
---

# mkfifo

> make fifos aka `named pipes``

## usage

```sh
mkfifo PIPE_NAME      # create named pipe

mkfifo PIPE_NAME -m700    # custom permissions

ls > PIPE_NAME
cat < PIPE_NAME


ls -lart PIPE_NAME      # notice 'p' in the beginning


{ ls -l && cat FILE; } >PIPE_NAME &


ls -l >PIPE_NAME &
cat FILE >PIPE_NAME &
cat <PIPE_NAME


{ pipedata="$(<PIPE_NAME)" && echo "$pipedata"; } &
ls >PIPE_NAME 
```

## see also

- [[script]]
- [[cat]]
