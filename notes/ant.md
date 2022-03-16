---
tags: [buildsystem, java]
title: ant
created: '2019-08-20T07:46:08.815Z'
modified: '2022-02-02T08:50:25.068Z'
---

# ant

> completely written in java - `ant` uses `xml` as build script

## usage

```sh
ant -version

ant compile

ant package

ant hello      # run target: hello
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

## see also

- [[mvn]]
- [[java]]
