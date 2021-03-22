---
title: aws
created: '2019-07-30T06:19:48.990Z'
modified: '2021-03-16T08:27:24.417Z'
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



aws ec2 describe-instances \
  --filters Name=instance-state-name,Values=running \
  --query "Reservations[*].Instances[*].InstanceId" --output text


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
