---
tags: [bsdmainutils]
title: hexdump
created: '2020-09-03T09:04:56.444Z'
modified: '2022-11-25T11:35:37.692Z'
---

# hexdump

> `hexdump` utility is a filter which displays specified files, or the STDIN, if no files are specified, in a user specified format

## option

```sh
-b                  # display one-byte octal 
-c                  # display One-byte character 
-C                  # display Canonical hex+ASCII 
-d                  # display Two-byte decimal 
-e FORMAT_STRING    # format string to be used for displaying data
-f FORMAT_FILE      # formatfile that contains one or more newline separated format strings
-n LENGTH           # Interpret only length bytes of input.
-o                  # display Two-byte octal 
-s offset           # skip offset bytes from the beginning of the input
-v                  # cause hexdump to display all input data
-x                  # display Two-byte hexadecimal 
```

# usage

```sh
echo hello | hexdump -v -e '/1 "%02X "' ;         # hex bytes: "68 65 6C 6C 6F 0A"

echo hello | hexdump -e '8/1 "%02X ""\t"" "' -e '8/1 "%c""\n"' # same, with ASCII section

echo hello | hexdump -v -e '"x" 1/1 "%02X" " "' ;       #  preceding x: x68 x65 x6C x6C x6F x0A

echo hello | hexdump -v -e '/1 "%02X\n"'                # one hex byte per line

printf ☠ | hexdump
```

## see also

- [[xxd]]
- [[od]]
- [[bash echo]]
- [[bash printf]]
