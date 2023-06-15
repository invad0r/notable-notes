---
tags: [container]
title: opa
created: '2021-03-16T15:13:29.336Z'
modified: '2023-05-25T16:01:44.936Z'
---

# opa

> `“oh-pa”` Open Policy Agent -general-purpose policy engine that unifies policy enforcement across the stack
> provides a high-level declarative language that lets you specify policy as code and simple APIs to offload policy decision-making from software
> can be used to enforce policies in microservices, k8s, cicd pipelines, api-gateways, etc.

## install

```sh
brew install opa
```

## usage

```sh
opa

opa eval 'x := 1; y := 2; x < y'
opa eval --data data.json 'name := data.names[_]'   # eval query against JSON data
opa eval --data file:///path/to/file.json 'data'    # eval query against JSON data supplied with a file:// URL:
```

## see also

- [[rego]]
- [[kubectl]]
- [github.com/open-policy-agent/opa/scanner.go](https://github.com/open-policy-agent/opa/blob/d3811e29eba10e9e79e8d517c2858be0dc2494fc/ast/internal/scanner/scanner.go)
