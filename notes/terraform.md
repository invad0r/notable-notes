---
tags: [iac]
title: terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2022-02-01T14:50:43.432Z'
---

# terraform

> tool for building, changing, and versioning infrastructure safely and efficiently

## usage

```sh
TF_LOG_PATH       #
TF_INPUT          #
TF_LOG            # TRACE, DEBUG, INFO, WARN or ERROR
TF_VAR_name       # e.g. "TF_VAR_region=us-west-1"

TF_LOG=DEBUG terraform apply &> log
```

```sh
terraform state -json | fx                                              # print whole state as json
terraform state list                                                    # check state
terraform state show 'module.path.data["name"] '                        # show state of resource
terraform state rm 'module.NAME'                                        # removes all associatd with module.Name
terraform state mv 'aws_vpc.ds-vpc' 'aws_vpc.ds_vpc'                    # rename resource
terraform state mv 'some_resource' 'module.app.some_resource'           # moves resource into module
terraform state mv 'module.app' 'module.parent.module.app'              # move module insid other module
terraform state mv -state-out=other.tfstate 'module.app' 'module.app'   # move module to other state

terraform 0.13upgrade .
terraform state replace-provider 'registry.terraform.io/-/happycloud' 'terraform.example.com/awesomecorp/happycloud'  # after upgrade to 0.13

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

> interactive repl for debuggin

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

## complex objects
```sh
resource "aws_route53_record" "example" {
  for_each = {
    for dvo in aws_acm_certificate.example.domain_validation_options : dvo.domain_name => {
      name    = dvo.resource_record_name
      record  = dvo.resource_record_value
      type    = dvo.resource_record_type
      zone_id = dvo.domain_name == "example.org" ? data.aws_route53_zone.example_org.zone_id : data.aws_route53_zone.example_com.zone_id
    }
  }

  allow_overwrite = true
  name            = each.value.name
  records         = [each.value.record]
  ttl             = 60
  type            = each.value.type
  zone_id         = each.value.zone_id
}

# variable "topic_subscriptions" {
#   description = "Map of topics for which the module should generate input queues including DLQ and subscriptions"
#   type = map(object({
#     topic_arn                  = string
#     name                       = optional(string)
#     queue_policy               = optional(string)
#     dlq_max_receive_count      = optional(number)
#     raw_message_delivery       = optional(bool)
#     visibility_timeout_seconds = optional(number)
#   }))
#   default = {}
# }

```

## see also

- [[tfswitch]]
- [[terrascan]]
- [[terraform cloud api]]
- [[dot]]
- [terraform.io/docs/configuration/resources](https://www.terraform.io/docs/configuration/resources.html#syntax)
- [terraform.io/docs/commands/environment-variables](https://www.terraform.io/docs/commands/environment-variables.html)
- [terraform.io/docs/cli/commands/state/mv](https://www.terraform.io/docs/cli/commands/state/mv.html)
- [[localstack]]
