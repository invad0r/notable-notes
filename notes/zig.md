---
tags: [zig]
title: zig
created: '2023-05-23T07:00:36.740Z'
modified: '2023-05-24T08:38:50.555Z'
---

# zig

> general-purpose programming language and toolchain for maintaining robust, optimal and reusable software

## usage

```sh
zig build-exe hello.zig
```

```zig
const std = @import("std");

pub fn main() !void {
    const stdout = std.io.getStdOut().writer();
    try stdout.print("Hello, {s}!\n", .{"world"});
}
```

## see also

- [[bun]]
- [[rust]], [[go]]
- [ziglang.org/](/https://ziglang.org/)
