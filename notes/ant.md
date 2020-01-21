---
tags: [buildtool, java]
title: ant
created: '2019-08-20T07:46:08.815Z'
modified: '2020-01-18T06:55:26.902Z'
---

# ant
> completely written in java - `ant` uses `xml` as build script

## usage
```sh
ant -version

ant compile

ant package
```

## target
```xml
<?xml version="1.0"?>
<project name="HelloWorld" default="hello">
    <target name="hello">
        <echo>Hello, World!</echo>
    </target>
</project>
```
```sh
ant hello      # run target: hello
```

## see also
- [[mvn]]
