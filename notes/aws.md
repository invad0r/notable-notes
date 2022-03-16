---
tags: [iac]
title: aws
created: '2019-07-30T06:19:48.990Z'
modified: '2022-03-04T07:31:25.433Z'
---

# aws

> aws cli - unified tool to manage your aws services

## install

`curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg" && installer -pkg ./AWSCLIV2.pkg -target /`

## environment variables

```sh
AWS_PROFILE                   # use profile from config
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_CONFIG_FILE               # default: "~/.aws/config"
AWS_SHARED_CREDENTIALS_FILE   # default:  ~/.aws/credentials
AWS_DEFAULT_OUTPUT            # json, yaml, yaml-stream, text, table
AWS_DEFAULT_REGION
```

[docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)

## flags

```sh
--color STRING              # support for color output: on, off, auto
--debug                     # enables debug logging by providing full python logs; (`CMD 2> FILE`, `CMD &> FILE`)
--regeion REGION            # override region

--dry-run
--output text
--owners amazon 
```

[docs.aws.amazon.com/cli/latest/userguide/cli-configure-options](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-options.html)

## usage

## configure

```sh
aws configure --profile PROFILE

aws --profile PROFILE --region us-east-1 COMMAND
```

```sh
[default]
credential_source=Ec2InstanceMetadata
```
[stackoverflow.com/replace-aws-keys-with-iam-role-in-aws-credentials](https://stackoverflow.com/a/50382297/14523221)

## security token service

```sh
aws sts get-caller-identity --query Account --output text     # get current account id
```

## identity and access management

```sh
aws iam list-roles --path-prefix /aws-service-role/config.amazonaws.com/    # get roles of service-link

aws iam list-policies --query 'Policies[PolicyName==`AmazonS3ReadOnlyAccess`].Arn'


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

## simple storage service

```sh
aws s3 list                                         # list buckets
aws s3 list s3://BUCKET                             # list objects in BUCKET
aws s3 ls s3://BUCKET --recursive
aws s3 rm s3://BUCKET --recursive

aws s3 cp   s3://BUCKET/KEY/FILE .                  # downlaod s3-object
aws s3 sync s3://BUCKET_1 s3://BUCKET_2 --dryrun    # diff two buckets

# aws s3api
aws s3api list-buckets | jq -r '.Buckets[].Name'
aws s3api list-buckets --query 'Buckets[*].Name'

aws s3api list-objects --bucket BUCKET | jq -r '.Contents[].Key'
aws s3api list-objects --bucket BUCKET --output text

aws s3api head-bucket --bucket BUCKET                       # return error if credentials aren't valid

aws s3api get-object-lock-configuration --bucket BUCKET	--query 'ObjectLockConfiguration.ObjectLockEnabled'   # check if lock config enables

aws s3api delete-objects --bucket BUCKET \
  --delete "$(aws s3api list-object-versions --bucket BUCKET | jq '{Objects: [.Versions[] | {Key:.Key, VersionId : .VersionId}], Quiet: false}')"


aws s3api delete-objects --bucket BUCKET \
  --delete "$( aws s3api list-object-versions --bucket BUCKET | jq -M '{Objects: [.["Versions","DeleteMarkers"][]|select(.Key == "key-value")| {Key:.Key,VersionId : .VersionId}], Quiet: false}' )"

aws s3api delete-objects --bucket BUCKET \
  --delete "$(aws s3api list-object-versions --bucket BUCKET | jq '{Objects: [.Versions[] | {Key:.Key, VersionId : .VersionId}], Quiet: false}')"

aws s3api delete-objects --bucket BUCKET \
  --delete "$(aws s3api list-object-versions --bucket BUCKET --query='{Objects: Versions[].{Key:Key,VersionId:VersionId}}')"

aws s3api delete-objects --bucket BUCKET \
  --delete "$(aws s3api list-object-versions --bucket BUCKET --query='{Objects: DeleteMarkers[].{Key:Key,VersionId:VersionId}}')"
```

## cloudfront

```sh
aws cloudfront list-cloud-front-origin-access-identities --output json
```

## elastic cloud compute

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

# find vpc dependencies when 'DependencyViolation' occure
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
```

## elastic kubernetes service

```sh
aws eks list-clusters

aws eks describe-cluster --name CLUSTER_NAME

aws eks describe-cluster `# get vpc id`\
	--name CLUSTER_NAME \
	--query "cluster.resourcesVpcConfig.vpcId" \
	--output text

aws eks get-token --cluster-name CLUSTER_NAME | jq -r '.status.token'

aws eks update-kubeconfig --region REGION --name CLUSTER_NAME
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

## simple message queuing service

```sh
aws sqs list-queues | jq '.QueueUrls[] | select(endswith("dlq"))' \
  | while read; do
    eval aws sqs get-queue-attributes --queue-url $REPLY --attribute-names All \
      | jq -r '.Attributes | select(.ApproximateNumberOfMessages | tonumber > 0) | "\(.ApproximateNumberOfMessages) \(.QueueArn)"'; 
    done
```

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

## securityhub

```sh
aws securityhub get-findings \
  --filter 'SeverityLabel={Value=CRITICAL,Comparison=EQUALS},ComplianceStatus={Value=FAILED,Comparison=EQUALS},ResourceType={Value=AwsS3Bucket,Comparison=EQUALS}' \
  | jq -r '.Findings[].Resources[].Id'

aws securityhub get-findings \
  --filters '{"GeneratorId":[{"Value": "aws-foundational","Comparison":"PREFIX"}],"WorkflowStatus": [{"Value": "NEW","Comparison":"EQUALS"}],"Confidence": [{"Gte": 85}]}' \
  --sort-criteria '{"Field": "LastObservedAt","SortOrder": "desc"}' \
  --page-size 5 --max-items 100
```

## see also

- [[aws-nuke]]
- [[eksctl]]
- [[amazon-linux-extras]]
- [[ec2-instance-selector]]
- [[mc]]
- [[kubectl]]
- [[gcloud]]
- [[jq]], [[yq]]
- [[installer]]
- [[localstack]], [[minikube]]
- [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html)
