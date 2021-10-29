---
title: fswatch
created: '2021-10-19T10:15:19.670Z'
modified: '2021-10-19T10:17:11.193Z'
---

# fswatch

> file change monitor that receives notifications when the contents of the specified files or directories are modified

## install 

`brew install fswatch`

## usage

```sh
fswatch . | xargs -n 1 -I {} echo {}
```

## see also

- [[watch]]
- [emcrisostomo.github.io/fswatch](https://emcrisostomo.github.io/fswatch/)
