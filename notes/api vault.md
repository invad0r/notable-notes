---
tags: [api]
title: api vault
created: '2019-09-26T06:09:05.847Z'
modified: '2022-03-16T05:42:35.850Z'
---

# api vault

> hashicorp vault api

## usage

```sh
curl \
    --header "X-Vault-Token: ..." \
    --request POST \
    --data @payload.json \
    http://127.0.0.1:8200/v1/pki/issue/my-role
```

## see also

- [[vault]]
- [[consul]]
- [[api consul]]
