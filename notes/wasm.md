---
title: wasm
created: '2020-08-19T07:23:59.679Z'
modified: '2022-02-02T10:03:31.300Z'
---

# wasm

> virtual instruction set architecture
> binary instruction format for stack-based virtual machine
> designed as portable target for compiliation of high-level langs like c, c++, rust

- brackets are called `s-expressions` (`lisp`) and used to represent tree-like structures
  -  root of the tree is a `module` (like `javascript` modules)
- basic building blocks of `wasm` are instructions that operate on the stack
- uses structured control flow (`if` `else` `loop`) and avoids `GOTO` jumps, which allows parsing source in one pass
- `wasm` uses `linear memory model` as memory addressing technique in which memory is organized in a single contagious address space. (aka flat memory model)
- `wasm` is compiled and executed on the fly, as the bytes stream in

## usage

```c
int sign(int x) { return (x % 2) * (2 - (x % 4)); }
```

```wasm
(func (;1;) (type 0) (param i32) (result i32)

                    ;; (2 - (x % 4))
  i32.const 2       ;; push values: integer 2
  local.get 0       ;; push first parameter of the function
  i32.const 4       ;; push values: integer 4
  i32.rem_s         ;; instruction removes two values from stack (first function parameter and the integer 4)
                    ;; divide first value by second then pushes the remainder back on stack
  i32.sub           ;; pops ramainder and 2 from stack and subtracts one from another, pushes the result

                    ;; (x % 2) * REMAINDER
  local.get 0
  i32.const 2
  i32.rem_s
  i32.mul)
```

## see also

- [[asm]]
- [[rust]]
- [[clang]]
- [[emcc]]
- [evilmartians.com/chronicles/hands-on-webassembly-try-the-basics](https://evilmartians.com/chronicles/hands-on-webassembly-try-the-basics)
