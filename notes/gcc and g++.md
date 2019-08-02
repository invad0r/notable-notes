---
tags: [lang]
title: gcc and g++
created: '2019-07-30T06:19:49.029Z'
modified: '2019-07-30T07:58:35.164Z'
---

# gcc and g++
```
1. pre-processing  =>  2. compiling    =>  3. assembly     => 4. linking
   output: file.i  =>  output: file.s  =>  output:file.o   => output: file
```

## gcc

```sh
gcc -o file_sum file_sum.c

gcc -Wall -g -O0 -o file_sum file_sum.c
```

## g++

```sh
g++ -std=c++11 vector-out-of-bounds.cpp -o vector-out-of-bounds
```
