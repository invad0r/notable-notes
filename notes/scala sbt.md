---
tags: [buildtool]
title: scala sbt
created: '2019-07-30T06:19:49.228Z'
modified: '2019-08-18T19:40:41.013Z'
---

# scala sbt

## env
```sh
export JAVA_HOME=$(/usr/libexec/java_home)
export SCALA_HOME=$(pwd)/scala-2.13.0-M1
export PATH=$PATH:$SCALA_HOME/bin
```

## repl - read evaluate print loop
```sh
scala> :help

scala> :reset  // clear past commands in session

scala> :type   // print type without evaluating
```

## sbt
`= simple build tool`
borrows from Ant, Maven and Gradle has REPL integration

- sbt terminology consists of two terms
  - tasks:      defines an action you perform like compile
  - settings:   defines a value like name and version of projekt

### 2 Modes
```sh
command-line mode     # run tasks and exits when finished e.g. sbt about
intaractive mode      # launch interactive sbt-shell
```

[sbt Reference Manual — Getting Started with sbt](http://www.scala-sbt.org/0.13/docs/Getting-Started.html)
[52-technologies-in-2016/README.md at master · shekhargulati/52-technologies-in-2016 · GitHub](https://github.com/shekhargulati/52-technologies-in-2016/blob/master/02-sbt/README.md)


## General Information

```sh
sbt sbtVersion                # find out version

sbt 'inspect sbtVersion'      # find out version

sbt about                     # find out version
```

### Tasks

tasks are run in parallel by default
```sh
help -v   # display additional settings
help -V   # display all settings

tasks -v    # Displays additional tasks.  More 'v's increase the number of tasks displayed.
tasks -V    # displays all tasks


sbt compile

sbt run

sbt reload        # after changes in build.sbt
```

### expressions and string
```scala
println(s"Age next year: ${age + 1}")      // any arbitrary expression can be embedded in ${}

println(s"You are 33 years old: ${age == 33}")

println(s"${hannah.name} has a score of ${hannah.score}")   // use curly braces when printing object fields
```
[String interpolation in Scala 2.10 and newer (String variable substitution) | alvinalexander.com](https://alvinalexander.com/scala/string-interpolation-scala-2.10-embed-variables-in-strings)
