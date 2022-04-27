---
title: kbst
created: '2022-03-23T06:54:40.598Z'
modified: '2022-03-23T08:58:32.352Z'
---

# kbst

> [[terraform]] framework for managed Kubernetes on AKS, EKS and GKE

## install

```sh
curl -LO "https://github.com/kbst/kbst/releases/download/$(curl -s https://www.kubestack.com/cli-latest.txt)/kbst_darwin_amd64.zip"
sudo unzip -d /usr/local/bin/ kbst_darwin_amd64.zip kbst
```

## usage

```sh
kbst help             # get help about any command

kbst local            # start localhost development env
kbst local apply      # bring up local development environment and start watching for changes
kbst local destroy

kbst manifest         # add, update and remove services from the catalog

kbst repository       # create and change Kubestack repositories
kbst repo init eks    # scaffold your repository using the EKS starter
```

## see also

- [[terraform]]
- [[localstack]]
- [[aws]]
