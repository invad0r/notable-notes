---
tags: [iac]
title: aws
created: '2019-07-30T06:19:48.990Z'
modified: '2022-12-05T14:51:00.473Z'
---

# aws

> aws cli - unified tool to manage your aws services

## install

```sh
curl -LO "https://awscli.amazonaws.com/AWSCLIV2.pkg" && installer -pkg ./AWSCLIV2.pkg -target /
```

## environment

```sh
AWS_ACCESS_KEY_ID                   # access key associated with an iam user or role
AWS_CA_BUNDLE                       # path to certificate bundle for HTTPS certificate validation
AWS_CLI_AUTO_PROMPT                 # enables auto-prompt, two settings can be used: on, on-partial
AWS_CLI_FILE_ENCODING               # encoding used for text files
AWS_CONFIG_FILE                     # location of the file that the AWS CLI uses to store configuration profiles. default: ~/.aws/config
AWS_DATA_PATH                       # list of additional directories to check outside of the built-in search path of ~/.aws/models
AWS_DEFAULT_OUTPUT                  # output format: json, yaml, yaml-stream, text, table
AWS_DEFAULT_REGION                  # aws region to send the request to
AWS_EC2_METADATA_DISABLED           # disables use of ec2 instance metadata service (IMDS)
AWS_MAX_ATTEMPTS                    # specifies a value of maximum retry attempts the AWS CLI retry handler uses
AWS_METADATA_SERVICE_NUM_ATTEMPTS   # attempts to retrieve credentials once from the instance metadata service before stopping
AWS_METADATA_SERVICE_TIMEOUT        # seconds before connection to instance metadata service should time out
AWS_PAGER                           # pager program used for output
AWS_PROFILE                         # name of profile with credentials and options
AWS_REGION                          # The AWS SDK compatible environment variable that specifies the AWS Region to send the request to
AWS_RETRY_MODE                      # Specifies which retry mode AWS CLI uses. There are three retry modes available: legacy (default), standard, and adaptive. 
AWS_ROLE_ARN                        # ARN of an IAM role with a web identity provider
AWS_ROLE_SESSION_NAME               # name to attach to the role session, provided to RoleSessionName parameter; used with AWS_ROLE_ARN and AWS_WEB_IDENTITY_TOKEN_FILE
AWS_SECRET_ACCESS_KEY               # secret key associated with the access key
AWS_SESSION_TOKEN                   # session token value that is required if you are using temporary security credentials retrieved directly from aws sts
AWS_SHARED_CREDENTIALS_FILE         # location of the file that the AWS CLI uses to store access keys. default path ~/.aws/credentials
AWS_STS_REGIONAL_ENDPOINTS          # how to determines aws service endpoint that the cli client uses to talk to the AWS Security Token Service
                                    # default value for version 1: "legacy" / version 2: "regional"
AWS_WEB_IDENTITY_TOKEN_FILE         # path to file containing an OAuth 2.0 access token or OpenID Connect ID token
```

[docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)

## flags

```sh
--color STRING              # support for color output: on, off, auto
--debug                     # enables debug logging by providing full python logs; (`CMD 2> FILE`, `CMD &> FILE`)
--region REGION             # override region
--dry-run
--output text               # json
--owners amazon
--profile PROFILE
--cli-auto-prompt, --no-cli-auto-prompt
```

[docs.aws.amazon.com/cli/latest/userguide/cli-configure-options](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-options.html)

## usage

## configure

```sh
aws configure
aws configure list
aws configure list-profiles

aws --profile PROFILE configure set region REGION
aws --profile PROFILE configure set default.region REGION
aws --profile PROFILE configure set aws_access_key_id ACCESS_KEY_ID
aws --profile PROFILE configure set aws_secret_access_key SECRET_ACCESS_KEY
aws --profile PROFILE configure set aws_session_token AWS_SESSION_TOKEN
```

```sh
cat <<EOF > ~/.aws/config
[profile PROFILE_NAME]
aws_cli_auto_prompt     = on|on-partial
aws_cli_file_encoding   = UTF-8
aws_session_token       =
ca_bundle               =
cli_pager               =
credential_source       = Ec2InstanceMetadata
max_attempts            =
output                  = json|yaml|yaml-stream|text|table
region                  = REGION
retry_mode              =
role_arn                = ROLE_ARN
role_session_name       =
source_profile          = PROFILE_NAME
web_identity_token_file =
EOF

cat <<EOF > ~/.aws/credentials
[PROFILE_NAME]
aws_access_key_id     = AWS_ACCESS_KEY_ID
aws_secret_access_key = AWS_SECRET_ACCESS_KEY
EOF
```

[stackoverflow.com/replace-aws-keys-with-iam-role-in-aws-credentials](https://stackoverflow.com/a/50382297/14523221)

## cloudtrail

```sh
aws cloudtrail lookup-events --max-results 1

aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=DescribeVpcs
#   AttributeKeys: AccessKeyId, EventId, EventName, EventSource, ReadOnly, ResourceName, ResourceType, Username
```

## configservice

```sh
aws configservice select-resource-config \
  --expression "SELECT resourceType GROUP BY resourceType" | jq -r '.Results[] | fromjson | .resourceType' | sort

aws securityhub get-findings \
  --filters <filter criteria JSON> \
  --sort-criteria <sort criteria> \
  --page-size <findings per page> \
  --max-items <maximum number of results>
```

## cloudfront

```sh
aws cloudfront list-cloud-front-origin-access-identities --output json
```

## cloudformation

```sh
aws cloudformation list-stacks --query "StackSummaries[*].StackName" --stack-status-filter \
  CREATE_IN_PROGRESS \
  CREATE_COMPLETE \
  ROLLBACK_IN_PROGRESS \
  ROLLBACK_FAILED \
  ROLLBACK_COMPLETE \
  DELETE_IN_PROGRESS \
  DELETE_FAILED \
  UPDATE_IN_PROGRESS \
  UPDATE_COMPLETE_CLEANUP_IN_PROGRESS \
  UPDATE_COMPLETE \
  UPDATE_ROLLBACK_IN_PROGRESS \
  UPDATE_ROLLBACK_FAILED \
  UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS \
  UPDATE_ROLLBACK_COMPLETE \
  REVIEW_IN_PROGRESS 
```

[[cdk]], [[cfn]], [[terraform]]

## ec2 - elastic cloud compute

```sh
aws ec2 describe-instances \
  --filters "Name=tag-key,Values=eks:cluster-name" "Name=tag-value,Values=eksworkshop*" \
  --query 'Reservations[*].Instances[*].[PrivateDnsName,Tags[?Key==`eks:nodegroup-name`].Value|[0],Placement.AvailabilityZone,PrivateIpAddress,PublicIpAddress]' \
  --output table   

aws ec2 describe-instances \
  --filters Name=instance-state-name,Values=running \
  --query "Reservations[*].Instances[*].InstanceId"
 
  --query 'Images[?CreationDate>=`2016-04-01`][]'
  --query "sort_by(Images, &CreationDate)[].Name"
  --query "sort_by(Images, &CreationDate)[].[Name, ImageId]"
  --query 'Images[*].[ImageId,CreationDate]' 
  --query 'sort_by(Images,&CreationDate)[-1].ImageId'
  --query 'reverse(sort_by(Images, &CreationDate))[0]'
  --query 'Images[*].[ImageId,CreationDate,Architecture]'
                            
--filters 'Name=name,Values=ubuntu/images/hvm-ssd/ubuntu-*-amd64-server-*' 'Name=state,Values=available'

# latest ubuntu 20 server arm64 image  => [-1:] returns the last element of the array
--filters "Name=name,Values=ubuntu*20.04-arm64-server*" \
  --query "sort_by(Images, &CreationDate)[-1:].[Name, ImageId]"

--filters "Name=name,Values=ubuntu/images/hvm-ssd/ubuntu-xenial-16.04*" \
  --query 'sort_by(Images, &CreationDate)[-1].[CreationDate,Name,ImageId]'

aws autoscaling describe-auto-scaling-groups \
  --query "AutoScalingGroups[? Tags[? (Key=='eks:cluster-name') && Value=='CLUSTER_NAME']].[AutoScalingGroupName, MinSize, MaxSize,DesiredCapacity]" \
  --output table

aws autoscaling describe-auto-scaling-groups `# get auto scaling group name` \
  --query "AutoScalingGroups[? Tags[? (Key=='eks:cluster-name') && Value=='CLUSTER_NAME']].AutoScalingGroupName" \
  --output text

aws autoscaling update-auto-scaling-group \
  --auto-scaling-group-name ASG_NAME \
  --min-size 3 --desired-capacity 3 --max-size 4 # increase/decrease capacities


aws ec2 create-security-group \
	--description 'RDS SG' \
	--group-name 'RDS_SG' \
	--vpc-id VPC_ID

aws ec2 describe-subnets `# get public subnet id's used by eks clsuter`\
  --filters "Name=vpc-id,Values=VPC_ID" "Name=tag:Name,Values=EKS_CLUSTER_NAME/SubnetPublic*" \
  --query 'Subnets[*].SubnetId' \
  --output json | jq -c .


aws ec2 describe-instance-types --instance-types m6i.large | jq
```

#### find vpc dependencies when 'DependencyViolation' occure

```sh
VPC="vpc-ID"

aws ec2 describe-internet-gateways
  --filters "Name=attachment.vpc-id,Values=$VPC" | jq -r '.InternetGateways[].InternetGatewayId'

aws ec2 describe-subnets
  --filters 'Name=vpc-id,Values='$VPC | grep SubnetId

aws ec2 describe-route-tables
  --filters 'Name=vpc-id,Values='$VPC | grep RouteTableId

aws ec2 describe-network-acls
  --filters 'Name=vpc-id,Values='$VPC | grep NetworkAclId

aws ec2 describe-vpc-peering-connections
  --filters 'Name=requester-vpc-info.vpc-id,Values='$VPC  | grep VpcPeeringConnectionId

aws ec2 describe-vpc-endpoints
  --filters 'Name=vpc-id,Values='$VPC | grep VpcEndpointId

aws ec2 describe-nat-gateways
  --filters 'Name=vpc-id,Values='$VPC | grep NatGatewayId

aws ec2 describe-security-groups
  --filters 'Name=vpc-id,Values='$VPC | grep GroupId

aws ec2 describe-instances
  --filters 'Name=vpc-id,Values='$VPC | grep InstanceId

aws ec2 describe-vpn-connections
  --filters 'Name=vpc-id,Values='$VPC | grep VpnConnectionId

aws ec2 describe-vpn-gateways
  --filters 'Name=attachment.vpc-id,Values='$VPC  | grep VpnGatewayId

aws ec2 describe-network-interfaces
  --filters 'Name=vpc-id,Values='$VPC | grep NetworkInterfaceId
```

### remove in-/egress rules from default secgroup

```sh
SEC_GROUP_ID="(aws ec2 describe-security-groups --filter Name=vpc-id,Values=vpc-09cb7d6df2e7f2e82 Name=group-name,Values=default --query 'SecurityGroups[*].[GroupId]' --output text)"

aws ec2 revoke-security-group-ingress --group-id $SEC_GROUP_ID \
  --ip-permissions "$(aws ec2 describe-security-groups --group-id $SEC_GROUP_ID --query "SecurityGroups[0].IpPermissions")"

aws ec2 revoke-security-group-egress --group-id $SEC_GROUP_ID \
  --ip-permissions "$(aws ec2 describe-security-groups --group-id sg-0e6d21618a794e886 --query "SecurityGroups[0].IpPermissionsEgress")"
```

### instance types

```sh
General Purpose       # most popular; used for web servers, development environments
Compute Optimized     # compute-intensive apps such as some scientific modeling or high-performance web servers
Memory Optimized      # memory-intensive apps, such as real-time big data analytics, or running Hadoop or Spark
Accelerated Computing # additional hardware (GPUs, FPGAs) to provide massive amounts of parallel processing for tasks such as graphics processing
Storage Optimized     # tasks that require huge amounts of storage, specifically with sequential read-writes, such as log processing
```

- [[ec2-instance-selector]]
- [[max-pods-calculator]]

## pricing

```sh
aws pricing describe-services --region us-east-1 | jq -r '.Services[] | .ServiceCode'
```

```sh
curl 'https://ec2.shop?region=us-west-2'
curl 'https://ec2.shop?region=us-west-2&filter=m4,m5,ssd'
curl 'https://ec2.shop' -H 'accept: json'
```

- [[ec2-instance-selector]]
- [ec2.shop](https://ec2.shop)
- [docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html)


## elastic load balancers

```sh
aws elb describe-load-balancers | jq '.LoadBalancerDescriptions[].LoadBalancerName'
```

## elastic kubernetes service

```sh
aws eks list-clusters

aws eks describe-cluster --name CLUSTER_NAME

aws eks describe-cluster --output text --name CLUSTER_NAME `# get vpc id` \
	--query "cluster.resourcesVpcConfig.vpcId" \

aws eks get-token --cluster-name CLUSTER_NAME | jq -r '.status.token'

aws eks update-kubeconfig --region REGION --name CLUSTER_NAME

aws eks describe-nodegroup --nodegroup-name NODE_GROUP-202200000012 --cluster-name CLUSTER_NAME
```

## ecs - elastic container service

```sh
aws ecs list-task-definitions | jq -r '.taskDefinitionArns[]'

aws ecs describe-tasks --tasks TASK

aws ecs put-account-setting-default \
  --name awsvpcTrunking \
  --value enabled \
  --region eu-central-1

aws ecs list-attributes \
  --target-type container-instance \
  --attribute-name ecs.awsvpc-trunk-id \
  --cluster base-cluster \
  --region eu-central-1

aws ecs execute-command --cluster CLUSTER --task TASK --container CONTAINER --interactive --command "bash"
```

[[ecs-cli]]

## iam - identity and access management

```sh
aws iam list-roles --path-prefix /aws-service-role/config.amazonaws.com/    # get roles of service-link

aws iam list-roles | jq -r '.Roles[] | "\(.RoleName): \(.AssumeRolePolicyDocument.Statement[].Principal?)"'

aws iam list-roles | jq '.Roles[] |  {role: .RoleName, user: .AssumeRolePolicyDocument.Statement[].Principal.AWS} | select(.user != null)'

aws iam list-policies --query 'Policies[PolicyName==`AmazonS3ReadOnlyAccess`].Arn'

aws iam list-users | jq '.Users[].UserName' \
  | xargs -I{} aws iam list-access-keys --user-name {} | jq -r '.AccessKeyMetadata[] | "\(.UserName) \(.AccessKeyId)"'

# aws allows assigning only one MFA device (virtual or hardware) to root accounts
# if the list-virtual-mfa-devices returns valid 
aws iam list-virtual-mfa-devices \
  --assignment-status Assigned \
  --query 'VirtualMFADevices[*].SerialNumber' arn:  mfa-device currently assigned is virtual, not hardware !
# if web console won't allow removal of mfa device
aws iam delete-virtual-mfa-device --serial-number "arn:aws:iam::ACCOUNT_ID:mfa/root-account-mfa-device"  

# aws iam - access advisor
aws iam generate-service-last-accessed-details --arn ARN   # returns job-id

aws iam get-service-last-accessed-details --job-id JOB_ID

aws iam create-policy \
  --policy-name POLICY_NAME \
  --policy-document file://~/PATH/TO/POLICY.json


aws iam put-group-policy \
  --group-name GROUPE_NAME \
  --policy-name POLICY_NAME \
  --policy-document POLICY_DOCUMENT

aws iam create-user --user-name USER_NAME

aws iam add-user-to-group --group-name GROUPE_NAME --user-name USER_NAME

aws iam get-group --group-name GROUP_NAME

aws iam create-access-key --user-name USER_NAME
```

## relational database service

```sh
# create RDS Postgresql instance
aws rds create-db-instance \
  --db-instance-identifier RDS_NAME \
  --db-name DB_NAME \
  --db-instance-class db.t3.micro \
  --engine postgres \
  --db-subnet-group-name SEC_GROUP_NAME \
  --vpc-security-group-ids $RDS_SG \
  --master-username NAME \
  --publicly-accessible \
  --master-user-password RDS_PASSWORD \
  --backup-retention-period 0 \
  --allocated-storage 20

aws rds describe-db-instances `# get current status of rds e.g. creating, available,..` \
  --db-instance-identifier RDS_NAME \
  --query "DBInstances[].DBInstanceStatus" \
  --output text

aws rds describe-db-instances `# get database endpoint` \
  --db-instance-identifier RDS_NAME \
  --query 'DBInstances[0].Endpoint.Address' \
  --output text

aws rds delete-db-instance \
  --db-instance-identifier RDS_NAME \
  --delete-automated-backups \
  --skip-final-snapshot
```

## dynamodb

```sh
aws dynamodb list-tables

aws dynamodb scan --table-name "TABLE" \
  --filter-expression "userId = :name" \
  --expression-attribute-values '{":name":{"S":"7b13....99ea"}}'
```

## route53

```
aws route53 list-hosted-zones | jq -r '.HostedZones[] | .Id, .Name'
```

## route53domains

```sh
aws --region us-east-1 route53domains list-domains # route53domains api has no global endpoint; only works at region us-east-1

aws --region us-east-1 route53domains get-domain-detail --domain-name DOMAIN | jq -r '.Nameservers[].Name'
```

## ssm - aw services systems manager

```sh
# get latest ecs-optimized amazon-linux 2 ami
aws ssm get-parameters --names /aws/service/ecs/optimized-ami/amazon-linux-2/recommended \
  | jq '.Parameters[].Value | fromjson'

aws ssm get-parameters --names /aws/service/ecs/optimized-ami/amazon-linux-2/recommended \
  --region eu-central-1 --query "Parameters[0].Value" | jq 'fromjson'
```

## sts - security token service

```sh
aws sts get-caller-identity --query Account --output text     # get current account id

aws sts get-access-key-info --access-key-id ACCESS_KEY_ID     # returns account id for specified access key id

aws --profile PROFILE sts get-session-token \
  --duration-seconds 900 `# 15min`\
  --serial-number arn:aws:iam::ACCOUNT:mfa/USER \
  --token-code ONETIMECODE

# example using mfa and aws-cli
export AWS_ACCESS_KEY_ID=AWS_ACCESS_KEY_ID AWS_SECRET_ACCESS_KEY=AWS_SECRET_ACCESS_KEY AWS_SESSION_TOKEN=AWS_SESSION_TOKEN
aws sts get-session-token --serial-number "arn:aws:iam::ACC_ID:mfa/user.name" --token-code "$(op get totp ID)"    # otp
```

## securityhub

```sh
aws securityhub get-findings \
  --filter 'SeverityLabel={Value=CRITICAL,Comparison=EQUALS},ComplianceStatus={Value=FAILED,Comparison=EQUALS},ResourceType={Value=AwsS3Bucket,Comparison=EQUALS}' \
  | jq -r '.Findings[].Resources[].Id'

aws securityhub get-findings \
  --filters '{"GeneratorId":[{"Value": "aws-foundational","Comparison":"PREFIX"}],"WorkflowStatus": [{"Value": "NEW","Comparison":"EQUALS"}],"Confidence": [{"Gte": 85}]}' \
  --sort-criteria '{"Field": "LastObservedAt","SortOrder": "desc"}' \
  --page-size 5 --max-items 100

aws securityhub get-findings \
  --filters '{"SeverityLabel":[{"Value": "HIGH","Comparison":"EQUALS"}],"WorkflowStatus": [{"Value":"NEW","Comparison":"EQUALS"}],"WorkflowStatus": [{"Value":"NOTIFIED","Comparison":"EQUALS"}]}' | jq -r '.Findings[].Resources[].Id'
```

## sqs - simple message queuing service

```sh
aws sqs list-queues | jq '.QueueUrls[] | select(endswith("dlq"))' \
  | while read; do
    eval aws sqs get-queue-attributes --queue-url $REPLY --attribute-names All \
      | jq -r '.Attributes | select(.ApproximateNumberOfMessages | tonumber > 0) | "\(.ApproximateNumberOfMessages) \(.QueueArn)"'; 
    done
```

## s3 - simple storage service

```sh
aws s3 list                                         # list buckets
aws s3 list s3://BUCKET                             # list objects in BUCKET
aws s3 ls s3://BUCKET --recursive
aws s3 rm s3://BUCKET --recursive

aws s3 cp   s3://BUCKET/KEY/FILE .                  # downlaod BUCKET object
aws s3 sync s3://BUCKET_1 .                         # download all objects to local dir
aws s3 sync s3://BUCKET_1 s3://BUCKET_2 --dryrun    # diff two buckets

# aws s3api
aws s3api list-buckets | jq -r '.Buckets[].Name'
aws s3api list-buckets --query 'Buckets[*].Name'

aws s3api list-objects --bucket BUCKET | jq -r '.Contents[].Key'
aws s3api list-objects --bucket BUCKET --output text

aws s3api head-bucket --bucket BUCKET                       # return error if credentials aren't valid

aws s3api get-object-lock-configuration --bucket BUCKET	--query 'ObjectLockConfiguration.ObjectLockEnabled'   # check if lock config enables


aws s3api delete-objects --bucket BUCKET \
  --delete "$(aws s3api list-object-versions --bucket BUCKET --query='{Objects: Versions[].{Key:Key,VersionId:VersionId}}')"

aws s3api delete-objects --bucket BUCKET \
  --delete "$(aws s3api list-object-versions --bucket BUCKET --query='{Objects: DeleteMarkers[].{Key:Key,VersionId:VersionId}}')"

# aws s3api list-object-versions --bucket BUCKET | jq '{Objects: [.Versions[] | {Key:.Key, VersionId : .VersionId}], Quiet: false}'
# aws s3api list-object-versions --bucket BUCKET | jq -M '{Objects: [.["Versions","DeleteMarkers"][]|select(.Key == "key-value")| {Key:.Key,VersionId : .VersionId}], Quiet: false}'
```

## see also

- [[cdk]]
- [[aws-nuke]]
- [[eksctl]]
- [[amazon-linux-extras]]
- [[ec2-instance-selector]]
- [[mc]]
- [[kubectl]]
- [[gcloud]]
- [[jq]], [[yq]]
- [[op]]
- [[installer]]
- [[localstack]], [[minikube]]
- [[installer]]
- [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html)
