---
tags: [java]
title: quarkus
created: '2023-03-14T12:54:49.416Z'
modified: '2023-03-22T11:04:05.459Z'
---

# quarkus

> cli for quarkus, which is a k8s native [[java]] framework tailored for OpenJDK HotSpot and GraalVM

## install

```sh
sdk install quarkus
```

## option

```sh

```

## env

```sh
QUARKUS_BANNER_ENABLED
```

## usage

```sh
quarkus

quarkus create app org.acme:getting-started --extension='resteasy-reactive'

quarkus:dev # runs dev mode, which enables live reload with background compilation

quarkus build --native --no-tests -Dquarkus.native.container-build=true

./mvnw install -Dnative -Dquarkus.native.container-build=true -Dquarkus.native.builder-image=quay.io/quarkus/ubi-quarkus-mandrel-builder-image:22.3-java17
./mvnw package -Pnative -Dquarkus.native.container-build=true -Dquarkus.container-image.build=true
```

## see also

- [[gu]]
- [[sdk]]
- [[mvn]]
- [[java]]
