---
tags: [container, packagemanager]
title: pack
created: '2023-04-24T08:05:09.255Z'
modified: '2023-05-05T06:58:38.046Z'
---

# pack

> tool maintained by the Cloud Native Buildpacks project to support the use of buildpacks

## install

```sh
brew install buildpacks/tap/pack
```

## usage

```sh
pack build test_img --path apps/test-app --builder cnbs/sample-builder:bionic
```

## see also

- [[mvn]]
- [[quarkus]]
- [[skopeo]]
- [buildpacks.io/docs/tools/pack](https://buildpacks.io/docs/tools/pack/)
