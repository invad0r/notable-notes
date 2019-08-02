---
tags: [bash, xml]
title: xmllint
created: '2019-08-01T08:20:39.353Z'
modified: '2019-08-01T08:55:16.385Z'
---

# xmllint


## xpath
```sh
cat <<EOF > /tmp/sourcefile.xml
<?xml version="1.0"?>
<footag>TastyGoodness</footag>
EOF

xmllint --xpath "string(//footag)" /tmp/sourcefile.xml
```

```sh
cat <<EOF > /tmp/testfile.xml
<?xml version="1.0" encoding="UTF-8" ?>
<!-- Component configuration file -->
<Component>
   <Name>install_env</Name>
   <HelpString>install_env Com</HelpString>
   <Version>1.10.3</Version>
</Component>
EOF

xmllint --xpath "//Component/Name/text()" /tmp/testfile.xml
```

## handling namspace

```sh
cat <<EOF > /tmp/namespace.xml
<?xml version="1.0" encoding="UTF-8" ?>
<chat xmlns="http://purl.org/net/ulf/ns/0.4-02" account="foo@bar.com" service="MSN">
<event type="windowOpened" sender="foo@bar.com" time="2011-11-22T00:34:43-03:00"></event>
<message sender="foo@bar.com" time="2011-11-22T00:34:43-03:00" alias="foo"><div><span style="color: #000000; font-family: Helvetica; font-size: 12pt;">hi</span></div></message>
</chat>
EOF

/tmp/namespace.xml

```
### shell mode and declare the namespace with a prefix
```sh
xmllint --shell /tmp/namespace.xml
    / > setns x=http://purl.org/net/ulf/ns/0.4-02
    / > xpath /x:chat
```
### local-name() to match element names
```sh
xmllint --xpath "/*[local-name()='chat']" /tmp/namespace.xml
```


### pom.xml

```sh
xmllint --shell pom.xml <<< 'setns ns=http://maven.apache.org/POM/4.0.0
cat /ns:project/ns:version/text()'

xmllint --xpath '/*[local-name()="project"]/*[local-name()="version"]/text()' pom.xml
```
[get-pom-xml-version-with-xmllint](https://stackoverflow.com/a/41115011/2087704)
