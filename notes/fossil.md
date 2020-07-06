---
title: fossil
created: '2020-07-02T06:23:57.933Z'
modified: '2020-07-02T06:32:31.760Z'
---

# fossil

> simple, high-reliability, distributed software configuration management system

> integrated bug-tracking, wiki, forum, technotes and built-in web ui
> single self-contained stand-alone executable
> uses ordinary http, https or ssh
> no server is required
> supports "autosync" mode
> stores content using an enduring file format in an SQLite database
> free and Open-Source

## usage
```sh
fossil init new-repository

fossil open new-repository

fossil add choices.xml

fossil commit -m "added choices.xml"

fossil ui
```
## see also
- [[git]]
- [[sqlite]]
