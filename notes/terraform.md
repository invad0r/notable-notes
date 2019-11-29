---
tags: [iac]
title: terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2019-10-31T15:17:22.557Z'
---

# terraform

## usage
```sh
TF_LOG=DEBUG terraform apply &> log


terraform state list        # check state

terraform state show module.path.data.foo.template


terraform fmt -diff -check  main.tf       # format configuration
```

## see also
- [Configuring Resources - Terraform by HashiCorp](https://www.terraform.io/docs/configuration/resources.html#syntax)
