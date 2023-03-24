---
tags: [json]
title: jless
created: '2022-05-17T19:12:45.216Z'
modified: '2023-03-22T10:28:04.370Z'
---

# jless

>  json viewer for reading, exploring, and searching through json data

## install

```sh
brew install jless

cargo install jless
```

## flags

```sh
-h, --help                     # print help information
-m, --mode MODE                # initial viewing mode. 
                               # --mode line  opening and closing curly and square brackets are shown and all Object keys are quoted
                               # --mode data (default), closing braces, commas, and quotes around Object keys are elided. 
                               # active mode can be toggled by pressing 'm' [default: data]
    --scrolloff SCROLLOFF      # number of lines to maintain as padding between the currently focused row and the top or bottom of the screen. Setting this to a large value will keep the focused in the middle of the screen (except at the start or end of a file) [default: 3]
-V, --version                  # print version information
    --json                     # parse input as JSON, regardless of file extension
    --yaml                     # parse input as YAML, regardless of file extension
```

## usage

```sh
alias yless="jless --yaml"

cat file.json | jless
```

## see also

- [[less]]
- [[jq]]
- [[fx]]
- [[cargo]]
- [jless.io](https://jless.io/)
