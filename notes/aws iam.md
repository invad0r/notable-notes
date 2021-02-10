---
pinned: true
title: aws iam
created: '2020-10-20T10:06:24.598Z'
modified: '2021-02-03T08:19:17.311Z'
---

# aws iam

> identity and access management

## usage
```sh
aws iam list-roles --path-prefix /aws-service-role/config.amazonaws.com/    # get roles of service-link


# aws allows assigning only one MFA device (virtual or hardware) to root accounts
# if the list-virtual-mfa-devices returns valid arn:  mfa-device currently assigned is virtual, not hardware !
aws iam list-virtual-mfa-devices --assignment-status Assigned --query 'VirtualMFADevices[*].SerialNumber'

# if web console won't allow removal of mfa device
aws iam delete-virtual-mfa-device --serial-number "arn:aws:iam::ACCOUNT_ID:mfa/root-account-mfa-device"


# access advisor
aws iam generate-service-last-accessed-details --arn ARN   # returns job-id

aws iam get-service-last-accessed-details --job-id JOB_ID
```

## see also
- [[aws]]
