---
tags: [buildtool, lang]
title: make
created: '2019-07-30T06:19:49.167Z'
modified: '2019-07-30T08:44:32.001Z'
---

# make

`Makefile.am` is a programmer-defined file and is used by `automake` to generate the `Makefile.in` file 

- `.am` stands for `automake`
- `.in` input for `configure` think of template

[what-are-makefile-am-and-makefile-in](https://stackoverflow.com/questions/2531827/what-are-makefile-am-and-makefile-in)
[confused-about-configure-script-and-makefile-in](https://stackoverflow.com/a/26832773/2087704)



```sh
make -f MyOtherMakefile     # specify other file
```

#### target

```make
.PHONY : clean      #  telling Make that this is a phony target, that it does not build anything

clean :
	rm -f *.dat
```

```sh
make clean    # call specific target
```

[Automation and Make: Introduction](http://swcarpentry.github.io/make-novice/01-intro/index.html)


## automake


[Using Autotools](https://developer.gnome.org/anjuta-build-tutorial/stable/create-autotools.html.en)
