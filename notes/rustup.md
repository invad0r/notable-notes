---
tags: [rust, versionmanager]
title: rustup
created: '2020-02-27T17:03:43.319Z'
modified: '2023-05-06T09:52:35.563Z'
---

# rustup

> rust toolchain installer

## install

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## usage

```sh
rustup show               # show active and installed toolchains or profiles

rustup doc --book         # open the documentation for the current toolchain

rustup self uninstall     # uninstall rust tooling und remove changes to .bashrc etc

rustup update
rustup update stable

rustup override set stable
```

## see also

- [[rust]]
- [[cargo]]
