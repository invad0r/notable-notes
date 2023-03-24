---
tags: [buildsystem, java]
title: sbt
created: '2019-07-30T06:19:49.228Z'
modified: '2023-03-23T08:44:44.431Z'
---

# sbt

> `simple build tool` for [[scala]]

## usage

sbt terminology consists of two terms:

- `tasks`: defines an action you perform like compile
- `settings`: defines a value like name and version of projekt

has two modes:
- `command-line`: run tasks and exits when finished e.g. `sbt about`
- `intaractive`: launch repl / interactive `sbt-shell`

```sh
sbt sbtVersion                # find out version
sbt 'inspect sbtVersion'      # find out version
sbt about                     # find out version


sbt compile

sbt run

sbt reload        # after changes in build.sbt
```

```sh
# tasks are run in parallel by default
help -v     # display additional settings
help -V     # display all settings

tasks -v    # Displays additional tasks.  More 'v's increase the number of tasks displayed.
tasks -V    # displays all tasks
```

## see also

- [[scala]]
- [scala-sbt.org/0.13/docs/Getting-Started](http://www.scala-sbt.org/0.13/docs/Getting-Started.html)
- [github.com/shekhargulati/52-technologies-in-2016/blob/master/02-sbt/README.md](https://github.com/shekhargulati/52-technologies-in-2016/blob/master/02-sbt/README.md)
- [[ant]] 
- [[mvn]] 
- [[gradle]]
- [[make]]

