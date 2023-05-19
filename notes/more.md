---
tags: [linux]
title: more
created: '2020-05-05T09:48:06.382Z'
modified: '2023-05-19T11:26:15.457Z'
---

# more

> file perusal filter for crt viewing 

## option

```sh
-V             # get version
--help         # show options
```

## usage

```sh
more -d file      # prompts `"[Press space to continue, 'q' to quit.]"`

more -s file      # squeeze multiple blank lines into one. 
```

## navigation

```sh
space     # scroll down
b         # scroll back/up
[n]k      # scoll back n lines
v         # start vi
```

## see also

- [[less]]
- [[man]]
