---
title: kubeval
created: '2021-03-18T09:10:51.860Z'
modified: '2021-03-18T09:17:25.494Z'
---

# kubeval

> validate one or more Kubernetes configuration files

## install
`brew tap instrumenta/instrumenta && brew install kubeval`

## usage
```sh
# flag
# --output=stdout     Plaintext
# --output=json       JSON
# --output=tap        TAP


kubeval FILE.yaml

cat FILE.yaml | kubeval                           # using stdin
cat FILE.yaml | kubeval --filename="FILE.yaml"    # make the output of pipelines more readable

kubeval --strict FILE.yaml    # simulates kubectl throwing error for k8s-api allows for specifying properties on objects that are not part of the schemas
```

## see also
- [[kubectl]]
