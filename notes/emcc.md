---
tags: [compiler]
title: emcc
created: '2020-08-31T13:19:52.268Z'
modified: '2023-03-22T08:25:30.577Z'
---

# emcc

> emscripten

## flags

```sh
-Os                                   # optimize for size: both for wasm and js
-s EXPORTED_FUNCTIONS='[..]'          #
  "_someFunc"                         # export from wasm-module (underscore required !)
  "_malloc", "_free"                  # functions will help us work with memory
-s EXPORTED_RUNTIME_METHODS='[..]'    #
  "ccall"                             # export ccall-function that emscripten generates for us
  MODULARIZE=1                        # allows use of global module function that returns promise with an instance of wasm module
```

## usage

```sh
emcc FILE.c -Os -o FILE.js \
  -s EXPORTED_FUNCTIONS='["_someFunc", "_malloc", "_free"]' \
  -s EXPORTED_RUNTIME_METHODS='["ccall"]' \
  -s MODULARIZE=1
```

## see also

- [[wasm]]
- [[rust]]
- [[clang]]
- [dassur.ma/things/c-to-webassembly](https://dassur.ma/things/c-to-webassembly/)
