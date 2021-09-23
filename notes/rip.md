---
tags: [rust]
title: rip
created: '2021-05-27T09:10:45.980Z'
modified: '2021-09-23T06:31:11.477Z'
---

# rip

> `rm ImProved` - cli deletion tool focused on safety, ergonomics, and performance
> does not implement the `xdg-trash`
> deleted files get sent to the graveyard (`/tmp/graveyard-$USER` by default

## install

`cargo install rm-improved`, `brew install rm-improved`

## usage

```sh
# flags
# -d, --decompose    permanently deletes (unlink) the entire graveyard

rip -u      # undo last deletion
```

## see also

- [github.com/nivekuil/rip](https://github.com/nivekuil/rip)
- [[rm]]
- [[unlink]]
- [[rust]]
- [[cargo]]
