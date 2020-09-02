---
tags: [buildsystem, c, go]
title: make
created: '2019-07-30T06:19:49.167Z'
modified: '2020-08-28T06:43:08.936Z'
---

# make

> works on the premise that you have specify a dependency, and then a rule to resolve that dependency [stackoverflow](https://stackoverflow.com/a/2209932/2087704)
> typically convert a main.c file to a main.o file then run `cc main.c`

> `Makefile.am` is a programmer-defined file and is used by `automake` to generate the `Makefile.in` file 

- `.am` stands for `automake`
- `.in` input for `configure` think of template

## usage

```sh
make -p                       # print default macros


make TARGET                   # run specific target

make -f MyOtherMakefile       # specify other file

make -B venv                  # always run target
```
## Makefile
```make
# macros / variables
# macros that are names of programs (such as CC)
#   CC       Program to compiling C programs; default is `cc`
#   LINT     Program to use to run lint on source code; default is `lint`
#   CPP      Program to running the C preprocessor, with results to standard output; default is `$(CC) -E'

# Macros that contain arguments of the programs
#   CFLAGS        Extra flags to give to the C compiler
#   CXXFLAGS      Extra flags to give to the C compiler
#   LINTFLAGS     Extra flags to give to lint

CC := gcc
CC := ${CC}

# `${CC}` and `$(CC)` are valid references to call `gcc`
# `:=` operator, also called the `simply expanded variable` to avoid infinite loops

all:
    @echo ${CC}


# target
.PHONY: clean      #  telling Make that this is a phony target, that it does not build anything

clean:
  @echo "Cleaning up..."    # suppress echoing the actual command place `@` before command
  rm *.txt
```

## see also
- [[cmake]]
- [[automake]]
- [[bundle rake]]
- [[gcc]]
- [tutorialspoint.com/.../makefile_macros.htm](https://www.tutorialspoint.com/makefile/makefile_macros.htm)
- [what-how-makefile](https://opensource.com/article/18/8/what-how-makefile)
- [what-are-makefile-am-and-makefile-in](https://stackoverflow.com/questions/2531827/what-are-makefile-am-and-makefile-in)
- [confused-about-configure-script-and-makefile-in](https://stackoverflow.com/a/26832773/2087704)
- [Automation and Make: Introduction](http://swcarpentry.github.io/make-novice/01-intro/index.html)
