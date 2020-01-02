---
tags: [buildtool, c, go]
title: make
created: '2019-07-30T06:19:49.167Z'
modified: '2020-01-02T13:05:31.126Z'
---

# make

> `Makefile.am` is a programmer-defined file and is used by `automake` to generate the `Makefile.in` file 

- `.am` stands for `automake`
- `.in` input for `configure` think of template

## usage

```sh
make -f MyOtherMakefile     # specify other file

make clean                  # run specific target

make -B venv                # always run target
```

### target
```make
.PHONY : clean      #  telling Make that this is a phony target, that it does not build anything

clean :
	rm -f *.dat
```

```make
clean:
  @echo "Cleaning up..."    # suppress echoing the actual command place `@` before command
  rm *.txt
```

## variables
- `${CC}` and `$(CC)` are valid references to call `gcc`
- `:=` operator, also called the `simply expanded variable` to avoid infinite loops
```make
CC := gcc
CC := ${CC}

all:
    @echo ${CC}
```

## patterns and functions

## see also
- [[gcc]]
- [[automake]]
- [what-how-makefile](https://opensource.com/article/18/8/what-how-makefile)
- [what-are-makefile-am-and-makefile-in](https://stackoverflow.com/questions/2531827/what-are-makefile-am-and-makefile-in)
- [confused-about-configure-script-and-makefile-in](https://stackoverflow.com/a/26832773/2087704)
- [Automation and Make: Introduction](http://swcarpentry.github.io/make-novice/01-intro/index.html)
- [[bundle rake]]
