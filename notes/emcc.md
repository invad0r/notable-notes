---
tags: [compiler]
title: emcc
created: '2020-08-31T13:19:52.268Z'
modified: '2022-02-02T10:14:11.064Z'
---

# emcc

> emscripten

## usage

```sh
-Os                                   # optimize for size: both for wasm and js
-s EXPORTED_FUNCTIONS='[..]'          #
  "_someFunc"                         # export from wasm-module (underscore required !)
  "_malloc", "_free"                  # functions will help us work with memory
-s EXPORTED_RUNTIME_METHODS='[..]'    #
  "ccall"                             # export ccall-function that emscripten generates for us
  MODULARIZE=1                        # allows use of global module function that returns promise with an instance of wasm module
```

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
