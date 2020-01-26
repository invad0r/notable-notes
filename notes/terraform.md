---
tags: [iac]
title: terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2020-01-23T07:08:28.826Z'
---

# terraform

## usage
```sh
TF_LOG=DEBUG terraform apply &> log

# vsphere provider specific variables
TF_VAR_vsphere_server
TF_VAR_vsphere_user
TF_VAR_vsphere_password


terraform state list        # check state

terraform state show module.path.data.foo.template


terraform fmt -diff -check  main.tf       # check format configuration
terraform fmt -write main.tf              # format config


terraform graph -draw-cycles -type=plan-destroy -module-depth=2 \
  | dot -Tsvg > graph.svg         # generate a visual representation of either a configuration or execution plan
                                  # -type TYPE     plan, plan-destroy, apply, validate, input, refresh
```

## see also
- [Configuring Resources - Terraform by HashiCorp](https://www.terraform.io/docs/configuration/resources.html#syntax)
- [[dot]]
- [[consul]]
