---
tags: [java, versionmanager]
title: sdk
created: '2019-08-20T08:05:04.309Z'
modified: '2023-05-11T06:24:19.206Z'
---

# sdk

> `sdkman` manage parallel versions of multiple sdk's - formerly known as `gvm` the `Groovy enVironment Manager`

## install

```sh
curl -s "https://get.sdkman.io" | bash
```

## env

```sh
SDKMAN_CANDIDATES_API       # https://api.sdkman.io/2
SDKMAN_CANDIDATES_DIR       # $HOME/.sdkman/candidates
SDKMAN_DIR                  # $HOME/.sdkman
SDKMAN_PLATFORM             # darwinx64
SDKMAN_VERSION              # 5.9.1+575
```

## usage

```sh
sdk help list

sdk current java

sdk ls java

sdk install sbt                     # latest version of sbt
sdk install java 11.0.4.hs-adpt     # use version
sdk install java 12.0.2.hs-adpt

sdk use java 12.0.2.hs-adpt

sdk default java 8.0.222.hs-adpt    # make default
```

## see also

- [[java]]
- [[scala]]
- [[gradle]]
- [[mvn]]
- [[gradle]]
- [[nvm]]
- [[quarkus]]
