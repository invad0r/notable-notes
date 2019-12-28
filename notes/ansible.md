---
tags: [iac]
title: ansible
created: '2019-07-30T06:19:27.514Z'
modified: '2019-12-25T20:58:07.634Z'
---

# ansible

## usage
```sh
ansible all -m ping -s    # adhoc command

ansible all -m shell -a 'cat /etc/*release'

ansible -i hosts all -m ping                        # uses local hosts file
```

## see also
- [[ansible-playbook]]
- [[ssh]]
