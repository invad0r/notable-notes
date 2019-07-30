---
tags: [iac]
title: ansible
created: '2019-07-30T06:19:27.514Z'
modified: '2019-07-30T09:06:44.963Z'
---

# ansible

## ansible adhoc

```sh
ansible all -m ping -s

ansible -i hosts all -m ping                        # uses local hosts file

ansibele all -m shell -a 'cat /etc/*release'
```

## ansible-playbook

```sh
ansible-playbook --syntax-check playbook.yml

ansible-playbook --list-hosts playbook.yml

ansible-playbook --list-tasks playbook.yml

ansible-playbook -i hosts ansible-bootstrap-ubuntu-16.04.yml    # bootstraps machine with python2
```
