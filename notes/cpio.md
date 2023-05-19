---
tags: [macos]
title: cpio
created: '2023-05-17T07:50:35.672Z'
modified: '2023-05-17T07:52:46.444Z'
---

# cpio

> copy files to and from archives

## option

```sh
-i      # input        - Read an archive from standard input (unless overridden) and extract the contents to disk or (if the -t option is specified) list the contents to standard output
-o      # output       - Read a list of filenames from standard input and produce a new archive on standard output (unless overridden) containing the specified items
-p      # pass-through - Read a list of filenames from standard input and copy the files to the specified directory
```

## usage

```sh
cat Payload | gunzip -dc | cpio -i
```

## see also

- [[xar]]
- [[gunzip]]
- [[installer]]
