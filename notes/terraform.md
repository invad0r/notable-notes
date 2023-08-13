---
tags: [iac]
title: terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2023-08-13T08:05:01.173Z'
---

# terraform

> tool for building, changing, and versioning infrastructure safely and efficiently

## install

```sh
tfswitch 0.14.4
```

## environment variables

```sh
TF_LOG_PATH       #
TF_INPUT          #
TF_LOG            # TRACE, DEBUG, INFO, WARN or ERROR
TF_VAR_name       # e.g. "TF_VAR_region=us-west-1"

TF_LOG=DEBUG terraform apply &> log
```
