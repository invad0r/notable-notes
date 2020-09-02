---
tags: [buildsystem, java]
title: gradle
created: '2019-08-20T07:46:19.821Z'
modified: '2020-08-28T06:43:08.919Z'
---

# gradle

> `gradle` is an advanced general purpose build management system based on `groovy` and `kotlin`

- `gradle` supports multi-project and multi-artifact builds
- `gradle` has the notion of `projects` and `tasks`


## install
```sh
sdk install gradle        # install the latest Gradle

sdk install gradle 3.0    # install a spefic gradle version
```

## usage
```sh
gradle -v, --version

gradle wrapper                          # create wrapper script: ./gradlew
gradle wrapper --gradle-version 4.9


gradle dependencies                     # show dependencies of project
./gradlew dependencies > dependencies.txt
```

## tasks

## dependencies

## see also
- [[sdkman]]
- [gradle-quickstart - nikgrozev.com](https://nikgrozev.com/2017/02/10/gradle-quickstart/)
