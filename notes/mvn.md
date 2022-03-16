---
tags: [buildsystem, java]
title: mvn
created: '2019-07-30T06:19:49.084Z'
modified: '2022-02-01T14:40:55.455Z'
---

# mvn

> `maven`, yiddish word meaning `accumulator of knowledge`, began as an attempt to simplify the build processes in the Jakarta Turbine project

## usage

```sh
--batch-mode      # 
```

```sh
mvn help:effective-pom -Doutput=effective-pom.xml

mvn help:describe -Dcmd=compile

# commands will automatically download and install the plugin if it hasn't already been installed
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list            # list  goals by the order they will execute
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list-phase      # group goals by phase
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list-plugin     # group goals by plugin
# default: goals search for tasks that run on `mvn deploy`, phases such as `clean` not included
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list -Dbuildplan.tasks=clean,install,deploy

mvn clean install

mvn clean deploy        # builds artefact and deploys to repository

mvn generate-sources

mvn clean install -DskipTests

mvn docker:push

mvn dependency:list > dependencies.txt`


# encryption
mvn --encrypt-master-password    
#   this goes into .m2/settings-security.xml
#   <settingsSecurity>
#     <master>{Pf5qrzaQNlMHkzYc74qsZ+bhvXmZj268aPdygg4YgF0=}</master>
#   </settingsSecurity>
mvn --encrypt-password          # server pass


# multi-module
mvn versions:set -newVersion=1.2.3


mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app \
  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

mvn package

# get version from pom.xml
mvn org.apache.maven.plugins:maven-help-plugin:2.1.1:evaluate -Dexpression=project.version \
  | grep -Ev "(^\[|Download[ed]\w+:)"
mvn --no-transfer-progress org.apache.maven.plugins:maven-help-plugin:2.1.1:evaluate -Dexpression=project.version \
  | grep -Ev "^\["
```

## see also

- [maven-in-five-minutes - apache.org](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)
- [Maven – Password Encryption](https://maven.apache.org/guides/mini/guide-encryption.html)
- [[sdk]]
- [[java]]
- [[gradle]]
- [[xmllint]]
- [[sbt]]
