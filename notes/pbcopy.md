---
tags: [macos]
title: pbcopy
created: '2019-07-30T06:19:49.205Z'
modified: '2023-03-22T09:28:47.588Z'
---

# pbcopy

> copy data from `stdin` to clipboard

## flags

```sh
-pboard {general | ruler | find | font}      # specifies pasteboard to copy or paste from. default: general

-Prefer {txt | rtf | ps}                     # what type of data to look for in the pasteboard first
```

## usage

```sh
pbcopy < FILE

echo STRING | pbcopy
```

## pbpaste

```sh
pbpaste

pbpaste >> FILE
```

## see also

- [ss64.com/osx/pbcopy](https://ss64.com/osx/pbcopy.html)
- [[screencapture]]
- [[cp]]
