---
title: aws
created: '2019-07-30T06:19:48.990Z'
modified: '2021-04-16T08:18:02.798Z'
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

aws --profile PROFILE --region us-east-1 COMMAND

# aws iam - identity and access management
aws iam list-roles --path-prefix /aws-service-role/config.amazonaws.com/    # get roles of service-link

# aws allows assigning only one MFA device (virtual or hardware) to root accounts
aws iam list-virtual-mfa-devices --assignment-status Assigned --query 'VirtualMFADevices[*].SerialNumber' # if the list-virtual-mfa-devices returns valid arn:  mfa-device currently assigned is virtual, not hardware !
aws iam delete-virtual-mfa-device --serial-number "arn:aws:iam::ACCOUNT_ID:mfa/root-account-mfa-device"   # if web console won't allow removal of mfa device

# aws iam - access advisor
aws iam generate-service-last-accessed-details --arn ARN   # returns job-id
aws iam get-service-last-accessed-details --job-id JOB_ID


# aws s3
aws s3 list                                         # list buckets
aws s3 list s3://BUCKET                             # list objects in BUCKET
aws s3 cp   s3://BUCKET/KEY/FILE .                  # downlaod s3-object
aws s3 sync s3://BUCKET_1 s3://BUCKET_2 --dryrun    # diff two buckets

# aws s3api
aws s3api list-objects --bucket BUCKET --output text
aws s3api head-bucket --bucket BUCKET                       # return error if credentials aren't valid


# ec2 describe-instances

--dry-run
--output text
--owners amazon 
--region eu-central-1

aws ec2 describe-instances --filters Name=instance-state-name,Values=running --query "Reservations[*].Instances[*].InstanceId"
 
--query 'Images[?CreationDate>=`2016-04-01`][]'
--filters "Name=name,Values=ubuntu*"                                                  --query "sort_by(Images, &CreationDate)[].Name"
--filters "Name=name,Values=ubuntu/images/*" --query "sort_by(Images, &CreationDate)[].[Name, ImageId]"
--filters "Name=name,Values=ubuntu/images/hvm-ssd/ubuntu-trusty-14.04-amd64*"         --query 'Images[*].[ImageId,CreationDate]' 
--filters "Name=name,Values=ubuntu/images/hvm-ssd/ubuntu-xenial-16.04-amd64-server-*" --query 'sort_by(Images,&CreationDate)[-1].ImageId'
--filters "Name=name,Values=amazon-eks-node-1.11*"                                    --query 'reverse(sort_by(Images, &CreationDate))[0]'
--filters 'Name=name,Values=ubuntu/images/hvm-ssd/ubuntu-*-amd64-server-*' 'Name=state,Values=available' --query 'Images[*].[ImageId,CreationDate,Architecture]' \
  | jq -r ‘.Images | sort_by(.CreationDate) | last(.[]).ImageId’
# latest ubuntu 20 server arm64 image  => [-1:] returns the last element of the array
--filters "Name=name,Values=ubuntu*20.04-arm64-server*"                               --query "sort_by(Images, &CreationDate)[-1:].[Name, ImageId]"
--filters "Name=name,Values=ubuntu/images/hvm-ssd/ubuntu-xenial-16.04*"               --query 'sort_by(Images, &CreationDate)[-1].[CreationDate,Name,ImageId]'

# find vpc dependencies when 'DependencyViolation' occure
VPC="vpc-ID"
aws ec2 describe-internet-gateways        --filters "Name=attachment.vpc-id,Values=$VPC"          | jq -r '.InternetGateways[].InternetGatewayId'
aws ec2 describe-subnets                  --filters 'Name=vpc-id,Values='$VPC                     | grep SubnetId
aws ec2 describe-route-tables             --filters 'Name=vpc-id,Values='$VPC                     | grep RouteTableId
aws ec2 describe-network-acls             --filters 'Name=vpc-id,Values='$VPC                     | grep NetworkAclId
aws ec2 describe-vpc-peering-connections  --filters 'Name=requester-vpc-info.vpc-id,Values='$VPC  | grep VpcPeeringConnectionId
aws ec2 describe-vpc-endpoints            --filters 'Name=vpc-id,Values='$VPC                     | grep VpcEndpointId
aws ec2 describe-nat-gateways             --filter 'Name=vpc-id,Values='$VPC                      | grep NatGatewayId
aws ec2 describe-security-groups          --filters 'Name=vpc-id,Values='$VPC                     | grep GroupId
aws ec2 describe-instances                --filters 'Name=vpc-id,Values='$VPC                     | grep InstanceId
aws ec2 describe-vpn-connections          --filters 'Name=vpc-id,Values='$VPC                     | grep VpnConnectionId
aws ec2 describe-vpn-gateways             --filters 'Name=attachment.vpc-id,Values='$VPC          | grep VpnGatewayId
aws ec2 describe-network-interfaces       --filters 'Name=vpc-id,Values='$VPC                     | grep NetworkInterfaceId


aws configservice select-resource-config --expression "SELECT resourceType GROUP BY resourceType" \
  | jq -r '.Results[] | fromjson | .resourceType' | sort



aws dynamodb list-tables

aws dynamodb scan --table-name "TABLE" \
  --filter-expression "userId = :name" \
  --expression-attribute-values '{":name":{"S":"7b13....99ea"}}'

# aws sqs - simple message queuing service
aws sqs list-queues | jq '.QueueUrls[] | select(endswith("dlq"))' \
  | while read; do
    eval aws sqs get-queue-attributes --queue-url $REPLY --attribute-names All \
      | jq -r '.Attributes | select(.ApproximateNumberOfMessages | tonumber > 0) | "\(.ApproximateNumberOfMessages) \(.QueueArn)"'; 
    done

# cloudtrail
aws cloudtrail lookup-events --max-results 1

# AccessKeyId
# EventId
# EventName
# EventSource
# ReadOnly
# ResourceName
# ResourceType
# Username
aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=DescribeVpcs




# aws securityhub
aws securityhub get-findings \
  --filters <filter criteria JSON> \
  --sort-criteria <sort criteria> \
  --page-size <findings per page> \
  --max-items <maximum number of results>

aws securityhub get-findings \
  --filter 'SeverityLabel={Value=CRITICAL,Comparison=EQUALS},ComplianceStatus={Value=FAILED,Comparison=EQUALS},ResourceType={Value=AwsS3Bucket,Comparison=EQUALS}' \
  | jq -r '.Findings[].Resources[].Id'

aws securityhub get-findings \
  --filters '{"GeneratorId":[{"Value": "aws-foundational","Comparison":"PREFIX"}],"WorkflowStatus": [{"Value": "NEW","Comparison":"EQUALS"}],"Confidence": [{"Gte": 85}]}' \
  --sort-criteria '{"Field": "LastObservedAt","SortOrder": "desc"}' \
  --page-size 5 --max-items 100
```

## see also
- [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html)
- [[installer]]
- [[mc]]
- [[gcloud]]
- [[jq]]
