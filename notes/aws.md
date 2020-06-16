---
tags: [cloud]
title: aws
created: '2019-07-30T06:19:48.990Z'
modified: '2020-06-10T09:07:12.695Z'
---

# aws

> aws cli - unified tool to manage your aws services

## install
`curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg" && installer -pkg ./AWSCLIV2.pkg -target /`

## usage
```sh
# [default]
# region = eu-central-1
# ouput = json
# cli_pager=

aws configure --profile PROFILE

aws s3 list --profile PROFILE --region us-east-1

aws s3api list-objects --bucket na-terraform-state --output text

aws ec2 describe-instances \
  --filters Name=instance-state-name,Values=running \
  --query "Reservations[*].Instances[*].InstanceId" --output text
```

## see also
- [[mc]]
- [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html)
- [[installer]]
