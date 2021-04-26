---
tags: [iac]
title: terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2021-03-30T06:55:05.054Z'
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

terraform state show module.path.data     # show state of resource

terraform state rm module.NAME                        # removes all associatd with module.Name

terraform state mv 'aws_vpc.ds-vpc' 'aws_vpc.ds_vpc'                    # rename resource
terraform state mv 'some_resource' 'module.app.some_resource'           # moves resource into module
terraform state mv 'module.app' 'module.parent.module.app'              # move module insid other module
terraform state mv -state-out=other.tfstate 'module.app' 'module.app'   # move module to other state

terraform validate -json                  # json-flag for showing all warnings, and where

terraform fmt -diff -check  main.tf       # check format configuration
terraform fmt -write main.tf              # format config


terraform graph | dot -Tsvg > graph.svg

terraform graph -draw-cycles -module-depth=2 
  -type=plan-destroy        `# -type=[plan|plan-destroy|apply|validate|input|refresh]` \
  | dot -Tsvg > graph.svg    # generate a visual representation of either a configuration or execution plan

terraform console     # startes repl-like console                               
```
## terraform console
```
> [ for d in local.developers: d.alternative_email ]      // iterate example

> data.aws_availability_zones.available                   // get value of data resource

> [ for N in list("a","b","c"): "eu-central-1${N}"]       // generate list of strings
[
  "eu-central-1a",
  "eu-central-1b",
  "eu-central-1c",
]

element(["a", "b", "c"], length(["a", "b", "c"])-1)       // get last element
```

## see also
- [[tfswitch]]
- [[terrascan]]
- [[terraform cloud api]]
- [[dot]]
- [terraform.io/docs/configuration/resources](https://www.terraform.io/docs/configuration/resources.html#syntax)
- [terraform.io/docs/commands/environment-variables](https://www.terraform.io/docs/commands/environment-variables.html)
- [terraform.io/docs/cli/commands/state/mv](https://www.terraform.io/docs/cli/commands/state/mv.html)
