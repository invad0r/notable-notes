---
tags: [c]
title: clang
created: '2020-08-27T10:58:10.930Z'
modified: '2023-03-25T12:52:52.956Z'
---

# clang

> [[c]], [[c++]], and [[objective-c]] compiler encompassing preprocessing, parsing, optimization, code generation, assembly, and linking

## flag

```sh
--target=wasm32         # tells a compiler to use WebAssembly as a target for compilation.
-03                     # applies a maximum amount of optimizations
-nostdlib               # tells not to use system libraries, as they are useless in the context of a browser.
-Wl,--no-entry          # tell linker to ignore the absence of main() /no entry function
-Wl,--export-all        # tell linker to export all the c functions from the webassembly module 
```

## usage

```sh
clang \
  --target=wasm32 \
  -O3  \
  -nostdlib \
  -Wl,--no-entry \
  -Wl,--export-all \
  -o FILE.wasm \
  FILE.c
```

## see also

- [[emcc]]
- [[c]]
- [[c++]]
- [[objective-c]]
- [[wasm]]
- [[make]]
