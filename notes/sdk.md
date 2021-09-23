---
tags: [java, versionmanager]
title: sdk
created: '2019-08-20T08:05:04.309Z'
modified: '2021-06-08T05:27:38.608Z'
---

# sdk

> `sdkman` manage parallel versions of multiple sdk's - formerly known as `gvm` the `Groovy enVironment Manager`

## install
`curl -s "https://get.sdkman.io" | bash`

## change java

```sh
SDKMAN_CANDIDATES_API       # https://api.sdkman.io/2
SDKMAN_CANDIDATES_DIR       # $HOME/.sdkman/candidates
SDKMAN_DIR                  # $HOME/.sdkman
SDKMAN_PLATFORM             # darwinx64
SDKMAN_VERSION              # 5.9.1+575
```

```sh
sdk install java 12.0.2.hs-adpt
sdk use java 12.0.2.hs-adpt
sdk current java

sdk ls java

sdk install sbt                     # latest version of sbt

sdk install java 11.0.4.hs-adpt     # use version

sdk default java 8.0.222.hs-adpt    # make default
```

## see also
- [[java]]
- [[gradle]]
- [[mvn]]
