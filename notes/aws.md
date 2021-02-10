---
title: aws
created: '2019-07-30T06:19:48.990Z'
modified: '2021-02-04T10:49:21.222Z'
---

# aws

> aws cli - unified tool to manage your aws services

## install
`curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg" && installer -pkg ./AWSCLIV2.pkg -target /`

## usage
```sh
# https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html
AWS_PROFILE                   # use profile from config
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_CONFIG_FILE               # default: "~/.aws/config"
AWS_SHARED_CREDENTIALS_FILE   # default:  ~/.aws/credentials
AWS_DEFAULT_OUTPUT            # json, yaml, yaml-stream, text, table
AWS_DEFAULT_REGION

# https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-options.html
# --color STRING      support for color output: on, off, auto
# --debug             enables debug logging by providing full python logs; (`CMD 2> FILE`, `CMD &> FILE`)



aws configure --profile PROFILE

aws s3 list --profile PROFILE --region us-east-1

aws s3api list-objects --bucket na-terraform-state --output text

aws ec2 describe-instances \
  --filters Name=instance-state-name,Values=running \
  --query "Reservations[*].Instances[*].InstanceId" --output text


aws configservice select-resource-config --expression "SELECT resourceType GROUP BY resourceType" \
  | jq -r '.Results[] | fromjson | .resourceType' | sort



aws dynamodb list-tables

aws dynamodb scan --table-name "TABLE" \
  --filter-expression "userId = :name" \
  --expression-attribute-values '{":name":{"S":"7b13....99ea"}}'
```

## see also
- [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html)
- [[installer]]
- [[mc]]
- [[gcloud]]
