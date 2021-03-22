---
tags: [iac]
title: terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2021-03-03T14:02:32.390Z'
---

# terraform

> tool for building, changing, and versioning infrastructure safely and efficiently

## usage
```sh
# environment variables
#   TF_LOG_PATH   
#   TF_INPUT
#   TF_LOG            TRACE, DEBUG, INFO, WARN or ERROR
#   TF_VAR_name       e.g. "TF_VAR_region=us-west-1"

TF_LOG=DEBUG terraform apply &> log

terraform state list                      # check state

terraform state show module.path.data


terraform validate -json                  # json-flag for showing all warnings, and where

terraform state rm module.NAME            # removes all associatd with module.Name

terraform fmt -diff -check  main.tf       # check format configuration
terraform fmt -write main.tf              # format config


terraform graph | dot -Tsvg > graph.svg

terraform graph \
  -draw-cycles \
  -type=plan-destroy \
  -module-depth=2 \
  | dot -Tsvg > graph.svg         # generate a visual representation of either a configuration or execution plan
                                  # -type TYPE     plan, plan-destroy, apply, validate, input, refresh
```
```
terraform console

[ for d in local.developers: d.alternative_email ]
```

## see also
- [[tfswitch]]
- [[terrascan]]
- [[terraform cloud api]]
- [[dot]]
- [terraform.io/docs/configuration/resources](https://www.terraform.io/docs/configuration/resources.html#syntax)
- [terraform.io/docs/commands/environment-variables](https://www.terraform.io/docs/commands/environment-variables.html)
