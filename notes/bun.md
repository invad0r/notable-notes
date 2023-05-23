---
tags: [javascript, runtime, zig]
title: bun
created: '2023-05-23T06:55:46.191Z'
modified: '2023-05-23T07:00:32.775Z'
---

# bun

> all-in-one toolkit for [[javascript]] and [[typescript]] apps

## install

```sh
brew tap oven-sh/bun && brew install bun
```

## usage

```sh
bun init

bun index.ts

bun test                      # run tests

bun run start                 # run the `start` script

bun install <pkg>​             # install a package

bunx cowsay "Hello, world!"   # execute a package


bun add -d bun-types    # add dev dependency to project
bun add figlet
bun add -d @types/figlet # TypeScript users only
```

## see also

- [[zig]]
- [[node]], [[js]], [[deno]]
- [[javascript]]
- [github.com/oven-sh/bun](https://github.com/oven-sh/bun)
