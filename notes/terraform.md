---
tags: [iac]
title: terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2023-03-22T09:52:22.099Z'
---

# terraform

> tool for building, changing, and versioning infrastructure safely and efficiently

## environment variables

```sh
TF_LOG_PATH       #
TF_INPUT          #
TF_LOG            # TRACE, DEBUG, INFO, WARN or ERROR
TF_VAR_name       # e.g. "TF_VAR_region=us-west-1"

TF_LOG=DEBUG terraform apply &> log
```

## usage

```sh
terraform state -json | fx                                              # print whole state as json

terraform state list                                                    # check state

terraform state show 'module.path.data["name"] '                        # show state of resource

terraform state rm 'module.NAME'                                        # removes all associatd with module.Name

terraform state mv 'aws_vpc.ds-vpc' 'aws_vpc.ds_vpc'                    # rename resource
terraform state mv 'some_resource' 'module.app.some_resource'           # moves resource into module
terraform state mv 'module.app' 'module.parent.module.app'              # move module insid other module
terraform state mv -state-out=other.tfstate 'module.app' 'module.app'   # move module to other state

terraform state replace-provider 'registry.terraform.io/-/happycloud' 'terraform.example.com/awesomecorp/happycloud'  # after upgrade to 0.13

terraform state list | grep PROVIDER_RESOURCE | sed 's/"/\\"/g' | xargs -I {} terraform state rm '{}'


terraform 0.13upgrade .


terraform validate -json                  # json-flag for showing all warnings, and where
terraform validate -json | jq '.diagnostics[] | {detail: .detail, filename: .range.filename, start_line: .range.start.line}'
terraform validate -json | jq -r '.diagnostics[] | "\(.address): \(.detail)"'
terraform validate -json \
  | jq -r '[ del( .diagnostics[] | select( .detail | startswith( "Experimental features" ) ) ) | .diagnostics[] | { Detail:.detail, Address:.address, Filename:.range.filename, Line:.range.start.line } ] | ( .[0] | keys_unsorted | ( . , map( length*"-" ) ) ), .[] | map(.) | @tsv' \
  | column -ts $'\t'


terraform fmt -diff -check  main.tf       # check format configuration

terraform fmt -write main.tf              # format config


terraform graph | dot -Tsvg > graph.svg

terraform graph -draw-cycles -module-depth=2 
  -type=plan-destroy        `# -type=[plan|plan-destroy|apply|validate|input|refresh]` \
  | dot -Tsvg > graph.svg    # generate a visual representation of either a configuration or execution plan

terraform console     # startes repl-like console       

```

## terraform console

> interactive repl for debugging

```tf
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

```tf
module "vpc" {
  ...
  private_subnets      = slice(cidrsubnets(var.vpc_cidr, 6, 6, 6, 6),0,2)
  public_subnets       = slice(cidrsubnets(var.vpc_cidr, 6, 6, 6, 6),2,4)
  ...
}
```

## complex objects

```tf
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

variable "topic_subscriptions" {
  description = "Map of topics for which the module should generate input queues including DLQ and subscriptions"
  type = map(object({
    topic_arn                  = string
    name                       = optional(string)
    queue_policy               = optional(string)
    dlq_max_receive_count      = optional(number)
    raw_message_delivery       = optional(bool)
    visibility_timeout_seconds = optional(number)
  }))
  default = {}
}
```

## provider tls

> allow private keys, certificates and certficate requests to be created as part of a terraform deployment

```hcl
resource "tls_private_key" "vault" {
  algorithm = "ECDSA"
}

resource "tls_self_signed_cert" "vault" {
  key_algorithm         = tls_private_key.vault.algorithm
  private_key_pem       = tls_private_key.vault.private_key_pem
  is_ca_certificate     = false
  validity_period_hours = 12
  early_renewal_hours   = 3

  # Reasonable set of uses for a server SSL certificate.
  # other X509v3 Key Usage: Certificate Sign, CRL Sign, Digital Signature, Non Repudiation, Key Encipherment, Data Encipherment
  allowed_uses = [
    "key_encipherment",
    "digital_signature",
    "server_auth",
  ]

  subject {
    common_name  = "common.name"
    organization = "organization"
  }
  dns_names = ["dns.name.1", "dns.name.2"]
}

resource "local_file" "cert_pem" {
  filename = "./files/${terraform.workspace}/certs/cert.pem"
  content  = tls_self_signed_cert.vault.cert_pem
}

resource "local_file" "key_pem" {
  filename = "./files/${terraform.workspace}/certs/key.pem"
  content  = tls_private_key.vault.private_key_pem
}

resource "null_resource" "provision_certs" {
  ..
  provisioner "file" {
    source      = local_file.cert_pem.filename
    destination = "/etc/vault/certs/cert.pem"
  }
}
```

[terraform.io/docs/providers/tls](https://www.terraform.io/docs/providers/tls/index.html)

## see also

- [[atlantis]]
- [[tfswitch]]
- [[terrascan]]
- [[terraform cloud api]]
- [[dot]]
- [terraform.io/docs/configuration/resources](https://www.terraform.io/docs/configuration/resources.html#syntax)
- [terraform.io/docs/commands/environment-variables](https://www.terraform.io/docs/commands/environment-variables.html)
- [terraform.io/docs/cli/commands/state/mv](https://www.terraform.io/docs/cli/commands/state/mv.html)
- [[localstack]]
- [[kbst]]
- [[tfk8s]]
- [[cdk]]
- [[iac]]
