---
tags: [packagemanager, rust]
title: cargo
created: '2020-02-27T16:59:23.781Z'
modified: '2023-05-10T14:12:38.092Z'
---

# cargo

> package manager for rust

## install

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
``` 

will add the [[cargo]], [[rustc]] and [[rustup]]

## usage

```sh
cargo install --list          # list installed crates
cargo install CRATE
cargo install-update CRATE

cargo build                   # build your project with 

cargo run                     # run your project with 

cargo test                    # test your project with 

cargo doc                     # build documentation for your project with 

cargo publish                 # publish a library to crates.io with 

cargo new hello-rust          # init new project


# fun projects
cargo install \
  exa \
  rm-improved \
  jless \
  gping \
  cargo-update \
  mdcat
  alacritty
```

## see also

- [[rust]]
- [[rustup]]
- [[exa]]
- [[rip]]
- [[jless]]
- [doc.rust-lang.org/cargo](https://doc.rust-lang.org/cargo/index.html)
