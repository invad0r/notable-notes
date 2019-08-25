---
tags: [buildtool, scala]
title: sbt
created: '2019-07-30T06:19:49.228Z'
modified: '2019-08-20T07:46:54.411Z'
---

# sbt

`simple build tool`

> borrows from [[ant]], [[mvn]] and [[gradle]] has a [[sbt repl]] integration.

sbt terminology consists of two terms:
- `tasks` - defines an action you perform like compile
- `settings` - defines a value like name and version of projekt

has 2 modes:
- `command-line`     - run tasks and exits when finished e.g. sbt about
- `intaractive`      - launch interactive sbt-shell


[Getting Started with sbt · scala-sbt.org](http://www.scala-sbt.org/0.13/docs/Getting-Started.html)
[52-technologies-in-2016/README.md · GitHub](https://github.com/shekhargulati/52-technologies-in-2016/blob/master/02-sbt/README.md)


## version

```sh
sbt sbtVersion                # find out version

sbt 'inspect sbtVersion'      # find out version

sbt about                     # find out version
```

### Tasks

tasks are run in parallel by default
```sh
help -v     # display additional settings
help -V     # display all settings

tasks -v    # Displays additional tasks.  More 'v's increase the number of tasks displayed.
tasks -V    # displays all tasks


sbt compile

sbt run

sbt reload        # after changes in build.sbt
```
