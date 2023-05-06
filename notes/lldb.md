---
tags: [c, macos]
title: lldb
created: '2023-05-04T15:35:31.448Z'
modified: '2023-05-04T15:54:55.975Z'
---

# lldb

> lldb is a fully featured debugger

## install

```sh
```

## usage

```sh
lldb /PATH/TO/FILE   # start with FILE
```

```c
# <noun> <verb> [-options [option-value]] [argument [argument...]]

(lldb) file ./helloworld            # load file

(lldb) breakpoint set -n main       # set breakpoint at function main

(lldb) breakpoint list


(lldb) process launch
(lldb) run
(lldb) r


(lldb) thread continue

(lldb) thread step-in    // The same as gdb's "step" or "s"
(lldb) thread step-over  // The same as gdb's "next" or "n"
(lldb) thread step-out   // The same as gdb's "finish" or "f"

(lldb) thread step-inst       // The same as gdb's "stepi" / "si"
(lldb) thread step-over-inst  // The same as gdb's "nexti" / "ni"
```

## see also

- [[gdb]]
- [[c]]
- [lldb.llvm.org/use/map](https://lldb.llvm.org/use/map.html)
- [lldb.llvm.org/use/tutorial](https://lldb.llvm.org/use/tutorial.html)
