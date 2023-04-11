---
tags: [javascript]
title: markdownlint
created: '2023-04-11T20:28:01.213Z'
modified: '2023-04-11T20:31:57.368Z'
---

# markdownlint

> markdown linter

## install

```sh
npm install -g markdownlint-cli
brew install markdownlint-cli

docker run -v $PWD:/workdir ghcr.io/igorshubovych/markdownlint-cli:latest "*.md"
```

## option

```sh
-V, --version                               # output the version number
-c, --config CONF                           # configuration file (JSON, JSONC, JS, or YAML)
-d, --dot                                   # include files/folders with a dot (for example `.github`)
-f, --fix                                   # fix basic errors (does not work with STDIN)
-i, --ignore [FILE|DIR|GLOB]                # file(s) to ignore/exclude (default: [])
-j, --json                                  # write issues in json format
-o, --output FILE                           # write issues to file (no console)
-p, --ignore-path FILE                      # path to file with ignore pattern(s)
-q, --quiet                                 # do not write issues to STDOUT
-r, --rules [FILE|DIR|GLOB|PACKAGE]         # include custom rule files (default: [])
-s, --stdin                                 # read from STDIN (does not work with files)
    --enable RULE                           # Enable certain rules, e.g. --enable MD013 MD041 --
    --disable RULE                          # Disable certain rules, e.g. --disable MD013 MD041 --
-h, --help                                  # display help for command
```

## usage

```sh
```

## see also

- [[markdown]]
- [[npm]]
