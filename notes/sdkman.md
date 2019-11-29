---
tags: [java, versionmanager]
title: sdkman
created: '2019-08-20T08:05:04.309Z'
modified: '2019-09-27T06:13:42.081Z'
---

# sdkman

> manage parallel versions of multiple sdk's - formerly known as `gvm` the `Groovy enVironment Manager`

## install
```sh
curl -s "https://get.sdkman.io" | bash      # lel
```

## change java
```sh
sdk ls java

sdk install sbt                     # latest version of sbt

sdk install java 11.0.4.hs-adpt     # use version

sdk default java 8.0.222.hs-adpt    # make default
```

## see also
- [[java]]
- [[gradle]]
