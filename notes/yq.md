---
tags: [yml]
title: yq
created: '2019-08-20T12:05:18.926Z'
modified: '2021-10-01T11:11:47.614Z'
---

# yq

> lightweight and portable command-line YAML processor

## install

`GO111MODULE=on go get github.com/mikefarah/yq/v3`

## usage

```sh
yq r file.yml services.application.image    # read file and print ..image

yq w -i -s ../update.yml file.yml           # write/update file
```

## see also

- [[yaml]]
- [[jq]]
- [[docker-compose]]
