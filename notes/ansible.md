---
tags: [iac]
title: ansible
created: '2019-07-30T06:19:27.514Z'
modified: '2022-02-02T08:50:08.080Z'
---

# ansible

> software provisioning, configuration management, and application-deployment tool enabling infrastructure as code

## usage

```sh
ansible all -m ping -s                              # adhoc command

ansible all -m shell -a 'cat /etc/*release'         # adhoc command using shell string

ansible -i hosts all -m ping                        # uses local hosts file
```

## see also

- [[ansible-playbook]]
- [[ssh]]
