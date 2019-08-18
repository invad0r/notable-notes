---
tags: [buildtool, lang/java]
title: java mvn
created: '2019-07-30T06:19:49.084Z'
modified: '2019-08-18T14:37:55.218Z'
---

# java mvn
`maven`

[maven-in-five-minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)

```sh
mvn clean install

mvn clean deploy        # builds artefact and deploys to repository

mvn help:effective-pom -Doutput=effective-pom.xml

```sh
mvn generate-sources


mvn clean install -DskipTests

mvn docker:push
```

## encryption
```sh
mvn --encrypt-master-password    # this goes into .m2/settings-security.xml

    # <settingsSecurity>
    #   <master>{Pf5qrzaQNlMHkzYc74qsZ+bhvXmZj268aPdygg4YgF0=}</master>
    # </settingsSecurity>

mvn --encrypt-password          # server pass
```
[Maven – Password Encryption](https://maven.apache.org/guides/mini/guide-encryption.html)
