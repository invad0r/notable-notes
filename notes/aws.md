---
tags: [iac]
title: aws
created: '2019-07-30T06:19:48.990Z'
modified: '2022-04-11T09:21:01.116Z'
---

# aws

> aws cli - unified tool to manage your aws services

## install

```sh
curl -LO "https://awscli.amazonaws.com/AWSCLIV2.pkg" && installer -pkg ./AWSCLIV2.pkg -target /
```

## environment variables

```sh
AWS_ACCESS_KEY_ID                   # access key associated with an IAM user or role
                                    # overrides profile setting: aws_access_key_id
AWS_CA_BUNDLE                       # path to a certificate bundle to use for HTTPS certificate validation.
                                    # overrides profile setting: ca_bundle
                                    # can override by --ca-bundle
AWS_CLI_AUTO_PROMPT                 # enables auto-prompt, two settings can be used:
                                    # `on`         uses full auto-prompt mode each time you attempt to run an aws command. This includes pressing ENTER after both a complete command or incomplete command.
                                    # `on-partial` uses partial auto-prompt mode. If a command is incomplete or cannot be run due to client-side validation errors, auto-prompt is used. This mode is particular useful if you have pre-existing scripts, runbooks, or you only want to be auto-prompted for commands you are unfamiliar with rather than prompted on every command.
                                    # aws_cli_auto_prompt=on      
                                    # aws_cli_auto_prompt=on-partial
                                    # overrides profile setting: cli_auto_prompt 
                                    # You can override this environment variable by using the --cli-auto-prompt and --no-cli-auto-prompt cli parameters

AWS_CLI_FILE_ENCODING               # encoding used for text files. By default encoding matches your locale
                                    # to set encoding different from the locale, use the aws_cli_file_encoding environment variable. For example, if you use Windows with default encoding CP1252, setting aws_cli_file_encoding=UTF-8 sets the CLI to open text files using UTF-8
AWS_CONFIG_FILE                     # location of the file that the AWS CLI uses to store configuration profiles. default: ~/.aws/config

AWS_DATA_PATH                       # list of additional directories to check outside of the built-in search path of ~/.aws/models when loading AWS CLI data
                                    # Setting this environment variable indicates additional directories to check first before falling back to the built-in search path. Multiple entries should be separated with the os.pathsep character, which is : on Linux or macOS and ; on Windows.
AWS_DEFAULT_OUTPUT                  # output format: json, yaml, yaml-stream, text, table
                                    # overrides profile setting: output
                                    # You can override this environment variable by using the --output cli parameter
AWS_DEFAULT_REGION                  # AWS Region to send the request to.
                                    # overrides profile setting: region
                                    # override by --region
AWS_EC2_METADATA_DISABLED           # Disables use of the Amazon EC2 instance metadata service (IMDS)
                                    # If set to true, user credentials or configuration (like the region) are not requested from IMDS
AWS_MAX_ATTEMPTS                    # Specifies a value of maximum retry attempts the AWS CLI retry handler uses, where the initial call counts toward the value that you provide. For more information on retries, see AWS CLI retries.
                                    # overrides profiles settin:g max_attempts
AWS_METADATA_SERVICE_NUM_ATTEMPTS   # attempts to retrieve credentials once from the instance metadata service before stopping
AWS_METADATA_SERVICE_TIMEOUT        # seconds before connection to instance metadata service should time out

AWS_PAGER                           # pager program used for output. By default, AWS CLI version 2 returns all output through your operating system’s default pager program.
                                    # unset to disable all use external paging program
                                    # overrides profile setting: cli_pager
AWS_PROFILE                         # name of profile with credentials and options
                                    # If defined, overrides the behavior of using the profile named [default] in the configuration file
                                    # You can override this environment variable by using the --profile cli parameter.
AWS_REGION                          # The AWS SDK compatible environment variable that specifies the AWS Region to send the request to.
                                    # If defined, overrides the values in the environment variable AWS_DEFAULT_REGION and the profile setting region
                                    # You can override this environment variable by using the --region cli parameter.
AWS_RETRY_MODE                      # Specifies which retry mode AWS CLI uses. There are three retry modes available: legacy (default), standard, and adaptive. For more information on retries, see AWS CLI retries.
                                    # overrides profiles settin:g retry_mode

AWS_ROLE_ARN                        # ARN of an IAM role with a web identity provider that you want to use to run the AWS CLI commands
                                    # Used with the AWS_WEB_IDENTITY_TOKEN_FILE and AWS_ROLE_SESSION_NAME environment variables
                                    # overrides profile setting: role_arn. You can't specify a role session name as a cli parameter
                                    # Note: this environment variable only applies to an assumed role with web identity provider it does not apply to the general assume role provider configuration.
                                    # For more information on using web identities, see Assume role with web identity.
AWS_ROLE_SESSION_NAME               # name to attach to the role session. value provided to the RoleSessionName parameter when the AWS CLI calls the AssumeRole operation, and becomes part of the assumed role user ARN: arn:aws:sts::123456789012:assumed-role/role_name/role_session_name
                                    # This is an optional parameter. If you do not provide this value, a session name is generated automatically. This name appears in AWS CloudTrail logs for entries associated with this session.
                                    # overrides profile setting: role_session_name
                                    # Used with the AWS_ROLE_ARN and AWS_WEB_IDENTITY_TOKEN_FILE environment variables.
                                    # For more information on using web identities, see Assume role with web identity.
                                    # Note: This environment variable only applies to an assumed role with web identity provider it does not apply to the general assume role provider configuration.
AWS_SECRET_ACCESS_KEY               # secret key associated with the access key. This is essentially the "password" for the access key.
                                    # overrides profile setting: aws_secret_access_key. You can't specify the secret access key ID as a cli option
AWS_SESSION_TOKEN                   # session token value that is required if you are using temporary security credentials that you retrieved directly from AWS STS operations
                                    # For more information, see the Output section of the assume-role command in the AWS CLI Command Reference
                                    # overrides profile setting: aws_session_token
AWS_SHARED_CREDENTIALS_FILE         # location of the file that the AWS CLI uses to store access keys. default path ~/.aws/credentials
                                    # You can't specify this value in a named profile setting or by using a cli parameter

AWS_STS_REGIONAL_ENDPOINTS          # how CLI determines AWS service endpoint that the AWS CLI client uses to talk to the AWS Security Token Service (AWS STS).
                                    # default value for version 1: "legacy"
                                    # – Uses global STS endpoint, sts.amazonaws.com, for the following AWS Regions: ap-northeast-1, ap-south-1, ap-southeast-1, ap-southeast-2, aws-global, ca-central-1, eu-central-1, eu-north-1, eu-west-1, eu-west-2, eu-west-3, sa-east-1, us-east-1, us-east-2, us-west-1, and us-west-2. All other Regions automatically use their respective regional endpoint
                                    # default value for version 2: "regional"
                                    # – The AWS CLI always uses the AWS STS endpoint for the currently configured Region. For example, if the client is configured to use us-west-2, all calls to AWS STS are made to the regional endpoint sts.us-west-2.amazonaws.com instead of the global sts.amazonaws.com endpoint. To send a request to the global endpoint while this setting is enabled, you can set the Region to aws-global.

AWS_WEB_IDENTITY_TOKEN_FILE         # path to a file that contains an OAuth 2.0 access token or OpenID Connect ID token that is provided by an identity provider
                                    # The AWS CLI loads the contents of this file and passes it as the WebIdentityToken argument to the AssumeRoleWithWebIdentity operation
                                    # Used with the AWS_ROLE_ARN and AWS_ROLE_SESSION_NAME environment variables
                                    # overrides profile setting: web_identity_token_file
```

[docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)

## flags

```sh
--color STRING              # support for color output: on, off, auto
--debug                     # enables debug logging by providing full python logs; (`CMD 2> FILE`, `CMD &> FILE`)
--region REGION             # override region

--dry-run
--output text
--owners amazon

--profile PROFILE

--cli-auto-prompt
--no-cli-auto-prompt 
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

aws sts get-access-key-info --access-key-id ASIA...4B5S       # returns account id for specified access key id

aws --profile PROFILE sts get-session-token \
  --duration-seconds 900 `# 15min`\
  --serial-number arn:aws:iam::ACCOUNT:mfa/USER \
  --token-code ONETIMECODE
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

aws iam list-users | jq '.Users[].UserName' \
  | xargs -I{} aws iam list-access-keys --user-name {} | jq -r '.AccessKeyMetadata[] | "\(.UserName) \(.AccessKeyId)"'
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


aws ec2 describe-instance-types --instance-types m6i.large | jq
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
- [[installer]]
- [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html)
