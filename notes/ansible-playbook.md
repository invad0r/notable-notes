---
tags: [iac]
title: ansible-playbook
created: '2019-11-28T11:53:47.807Z'
modified: '2019-12-25T20:04:08.815Z'
---

# ansible-playbook

> runs ansible playbooks, executing the defined tasks on the targeted hosts.

## usage
```sh
ansible-playbook --syntax-check playbook.yml

ansible-playbook --list-hosts playbook.yml

ansible-playbook --list-tasks playbook.yml

ansible-playbook -i hosts ansible-bootstrap-ubuntu-16.04.yml    # bootstraps machine with python2
```

## see also
- [[ansible]]
