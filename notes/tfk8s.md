---
tags: [container, iac]
title: tfk8s
created: '2022-03-29T16:03:27.046Z'
modified: '2023-03-22T10:33:23.155Z'
---

# tfk8s

> transform kubernetes manifst to hcl

## install

```sh
brew install tfk8s
```

## flags

```sh
-f, --file string         # file containing Kubernetes yaml manifests (default "-")
-M, --map-only            # output only an HCL map structure
-o, --output string       # output file to write Terraform config (default "-")
-p, --provider provider   # provider alias to populate the provider attribute
-s, --strip               # strip out server side fields - use if you are piping from kubectl get
-V, --version             # show version
```

## usage

```sh
tfk8s -f input.yaml -o output.tf

cat input.yaml | tfk8s > output.tf

kubectl get ns default -o yaml | tfk8s -M           # output maps instead of yaml

helm template ./chart-path -f values.yaml | tfk8s   # convert a helm chart to terraform
```

## see also

- [[go]]
- [[terraform]]
- [[iam-policy-json-to-terraform]]
- [[helm]]
- [github.com/jrhouston/tfk8s](https://github.com/jrhouston/tfk8s)
