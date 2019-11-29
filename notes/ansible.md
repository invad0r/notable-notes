---
tags: [iac]
title: ansible
created: '2019-07-30T06:19:27.514Z'
modified: '2019-11-28T11:53:44.809Z'
---

# ansible

## usgae
```sh
ansible all -m ping -s    # adhoc command

ansible -i hosts all -m ping                        # uses local hosts file

ansibele all -m shell -a 'cat /etc/*release'
```

## see also
- [[ansible-playbook]]
