---
tags: [cloud]
title: session-manager-plugin
created: '2022-09-30T07:14:39.638Z'
modified: '2023-03-24T08:27:11.783Z'
---

# session-manager-plugin

## install

```sh
curl -O "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/mac/sessionmanager-bundle.zip"
unzip sessionmanager-bundle.zip
sudo ./sessionmanager-bundle/install -i /usr/local/sessionmanagerplugin -b /usr/local/bin/session-manager-plugin


yum install -y session-manager-plugin.rpm
```

## usage

```sh
session-manager-plugin              # verify isntalled correctly

aws ssm start-session --target INSTANCE_ID

session-manager-plugin --version
```

## see also

- [[aws]]
- [[ecs-cli]]
