---
tags: [buildtool, java]
title: mvn
created: '2019-07-30T06:19:49.084Z'
modified: '2020-03-02T07:20:23.911Z'
---

# mvn

> `maven`, Yiddish word meaning `accumulator of knowledge`, began as an attempt to simplify the build processes in the Jakarta Turbine project

## usage
```sh
mvn clean install

mvn clean deploy        # builds artefact and deploys to repository

mvn help:effective-pom -Doutput=effective-pom.xml


mvn generate-sources

mvn clean install -DskipTests

mvn docker:push


mvn dependency:list > dependencies.txt`


# encryption
mvn --encrypt-master-password    # this goes into .m2/settings-security.xml

    # <settingsSecurity>
    #   <master>{Pf5qrzaQNlMHkzYc74qsZ+bhvXmZj268aPdygg4YgF0=}</master>
    # </settingsSecurity>

mvn --encrypt-password          # server pass


# multi-module
mvn versions:set -newVersion=1.2.3
```

## see also
- [maven-in-five-minutes - apache.org](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)
- [Maven – Password Encryption](https://maven.apache.org/guides/mini/guide-encryption.html)
- [[xmllint]]
- [[sbt]]
