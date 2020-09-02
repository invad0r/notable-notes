---
tags: [linux, macos]
title: zip unzip
created: '2019-09-26T06:55:59.693Z'
modified: '2020-09-01T07:18:06.284Z'
---

# zip unzip

> package and compress (archive) files

## usage
```sh
zip -r FILE.zip FILE/                                         # recursively zip all files in dir

unzip FILE.zip

unzip -l FILE.jar                                             # list files of jar

unzip -p FILE.jar META-INF/MANIFEST.MF                        # get current versions

zip -d FILE.jar BOOT-INF/classes/logback/logback-spring.xml   # remove file out of jar
```
## see also
- [[tar]]
- [[gzip gunzip zcat]]
- [[zrun]]
- [[jar]]
