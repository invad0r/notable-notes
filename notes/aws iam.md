---
title: aws iam
created: '2020-10-20T10:06:24.598Z'
modified: '2020-10-26T07:41:38.429Z'
---

# aws iam

## usage
```sh
aws iam list-roles --path-prefix /aws-service-role/config.amazonaws.com/    # get roles of service-link


# aws allows assigning only one MFA device (virtual or hardware) to root accounts
# if the list-virtual-mfa-devices returns valid arn:  mfa-device currently assigned is virtual, not hardware !
aws iam list-virtual-mfa-devices --assignment-status Assigned --query 'VirtualMFADevices[*].SerialNumber'


```
## see also
- [[aws]]
