---
tags: [buildtool, scala]
title: sbt
created: '2019-07-30T06:19:49.228Z'
modified: '2020-03-02T07:00:34.094Z'
---

# sbt

> `simple build tool` for scala

## usage
```sh
# sbt terminology consists of two terms:
#   tasks             defines an action you perform like compile
#   settings          defines a value like name and version of projekt
# has 2 modes:
#   command-line      run tasks and exits when finished e.g. sbt about
#   intaractive       launch interactive sbt-shell


sbt sbtVersion                # find out version
sbt 'inspect sbtVersion'      # find out version
sbt about                     # find out version


# tasks are run in parallel by default
help -v     # display additional settings
help -V     # display all settings

tasks -v    # Displays additional tasks.  More 'v's increase the number of tasks displayed.
tasks -V    # displays all tasks


sbt compile

sbt run

sbt reload        # after changes in build.sbt
```

## see also
- [[scala]]
- [Getting Started with sbt · scala-sbt.org](http://www.scala-sbt.org/0.13/docs/Getting-Started.html)
- [52-technologies-in-2016/README.md · GitHub](https://github.com/shekhargulati/52-technologies-in-2016/blob/master/02-sbt/README.md)
- [[ant]] 
- [[mvn]] 
- [[gradle]] 

