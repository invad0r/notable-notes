---
tags: [yml]
title: yq
created: '2019-08-20T12:05:18.926Z'
modified: '2019-10-23T14:24:27.024Z'
---

# yq

> lightweight and portable command-line YAML processor

## usage

### update inplace via script
```sh
yq r file.yml services.application.image    # read file and print ..image

yq w -i -s ../update.yml file.yml           # write/update file
```

## see also
- [[jq]]
