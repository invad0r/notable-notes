---
tags: [yml]
title: yq
created: '2019-08-20T12:05:18.926Z'
modified: '2019-08-20T12:10:03.772Z'
---

# yq

> similar to [[jq]]

### update inplace via script
```sh
# ../update-deploy.yml
# services.application.deploy.mode: replicated
# services.application.deploy.replicas: 0

yq w -i -s ../update.yml file.yml
```


```sh
yq r file.yml services.application.image
```
