---
tags: [linux, macos]
title: zip unzip
created: '2019-09-26T06:55:59.693Z'
modified: '2020-03-24T13:02:31.415Z'
---

# zip unzip

> package and compress (archive) files

## usage
```sh
zip -r 4d-app.zip 4d-app/   # recursively zip all files in dir

unzip 4d-app-zip

unzip -l file.jar     # list files of jar
zip -d file.jar BOOT-INF/classes/logback/logback-spring.xml # remove file out of jar
```
## see also
- [[tar]]
- [[gzip gunzip zcat]]
- [[jar]]
