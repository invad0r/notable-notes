---
tags: [java, repl]
title: jshell
created: '2023-05-15T07:28:53.482Z'
modified: '2023-05-24T08:42:49.265Z'
---

# jshell

> java repl, introdcues in jdk 9, executes constructs like class, interface, enum, object, statements, etc.

## option

```sh
--class-path PATH                # specify where to find user class files
--module-path PATH               # specify where to find application modules
--add-modules MODULE[,MODULE..]  # Specify modules to resolve, or all modules on the module path if <module> is ALL-MODULE-PATHs
--enable-preview                 # allow code to depend on preview features of this release
--startup FILE                   # one run replacement for the startup definitions
--no-startup                     # do not run the startup definitions
--feedback MODE                  # specify the initial feedback mode. The mode may be predefined (silent, concise, normal, or verbose) or previously user-defined
-q                               # quiet feedback.         Same as: --feedback concise
-s                               # really quiet feedback.  Same as: --feedback silent
-v                               # verbose feedback.       Same as: --feedback verbose
-JFLAG                           # pass FLAG directly to the runtime system. Use one -J for each runtime flag or flag argument
-RFLAG                           # pass FLAG to the remote runtime system.   Use one -R for each remote flag or flag argument
-CFLAG                           # pass FLAG to the compiler.                Use one -C for each compiler flag or flag argument
--version                        # print version information and exit
--show-version                   # print version information and continue
--help, -?, -h                   # print this synopsis of standard options and exit
--help-extra, -X                 # print help on non-standard options and exit
```

## usage

```sh
jehell              # start repl
```

## console

```java
jshell> /help      // display help
jshell> /? env     // get info on env command
jshell> /!         // rerun last snippet
jshell> /exit      // exit

jshell> int i = 123
i ==> 123

jshell> i + 456
$2 ==> 579

jshell> System.out.println("hello")
hello

jshell> for (var i = 0; i < 3; ++i)
   ...>    System.out.println(i*i)
```

## see also

- [[java]]
- [[node]]
