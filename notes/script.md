---
tags: [linux, macos]
title: script
created: '2021-06-16T15:51:41.553Z'
modified: '2023-03-24T09:51:00.666Z'
---

# script

> record everything printed on your terminal

## install

```sh
brew    install util-linux
apt-get install circos-tools 
```

## flag

```sh
-a          # append output to FILE or typescript
-d          # When playing back a session with the -p flag, do not sleep between records when playing back a timestamped session
-F PIPE     # immediately flush output after each write - allow to create a named pipe using `mkfifo` and another user may watch the live session using a utility like cat
-k          # Log keys sent to the program as well as output
-p          # Play back a session recorded with the -r flag in real time
-q          # Run in quiet mode, omit the start, stop and command status messages
-r          # Record a session with input, output, and timestamping
-t TIME     # specify the interval at which the script output file will be flushed to disk, in seconds.  
            # value of 0 causes script to flush after every character I/O event.  default: 30s
```

## usage

```sh
script RECORDING_NAME       # start recording

script -a RECORDING_NAME    # don't overwrite previous recording

script - -timing=timing_file FILE
```

## see also

- [[asciinema]]
- [[mkfifo]]
- [[cat]]
- [[screencapture]]
