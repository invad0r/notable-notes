---
tags: [compiler, dart]
title: dart
created: '2023-05-12T08:08:04.263Z'
modified: '2023-05-13T15:14:29.542Z'
---

# dart

> client-optimized language for developing multi-platform apps

- type safe, static type checking
- sound null safety, values can't be null, unless required
- dartvm offers a jit-compiler with incremental recompilation (enabling hot reload)
- dart aot-compiler can compile to native ARM or x64 machine code

## install

```sh
brew tap dart-lang/dart
brew install dart
```

## install

```sh
dart create -t console cli      # create project using console template

dart analyze

dart test

dart run                        # run programm

dart pub get                    # download dependencies after adding

dart compile exe bin/cli.dart   # compile to binary
```

## see also

- [dart.dev/overview](https://dart.dev/overview)
