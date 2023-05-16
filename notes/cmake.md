---
tags: [buildsystem, c, linux, macos]
title: cmake
created: '2020-08-27T11:35:46.274Z'
modified: '2023-05-08T11:07:28.173Z'
---

# cmake

> generator of buildsystems - can produce `Makefile`, `ninja` build files, etc. from same `CMakeLists.txt`

## install

```sh
brew install cmake
```

## usage

```sh
cmake -version

cmake .
```

## CMakeLists.txt

```txt
cmake_minimum_required(VERSION 2.8.9)
project (hello)
add_executable(hello helloworld.cpp)
```

## see also

- [[git]]
- [[make]]
- [[ninja]]
- [[clang]]
- [[gcc]]
- [[rust]]
- [stackoverflow.com/.../difference-between-using-makefile-and-cmake-to-compile-the-code](https://stackoverflow.com/questions/25789644/difference-between-using-makefile-and-cmake-to-compile-the-code/25790020)
