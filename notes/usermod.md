---
tags: [linux]
title: usermod
created: '2019-11-22T19:13:02.970Z'
modified: '2020-03-23T12:18:39.408Z'
---

# usermod

> modify a user account

## usage

```sh
usermod -aG docker

usermod -a -G GROUPNAME USERNAME          # -a    append
usermod -g PRIMARYGROUPNAME USERNAME      # -g    primary group assigned to the users
usermod -G SECONDARYGROUPNAME USERNAME    # -G    Other groups the user belongs to

groupadd fooadmin
usermod -d /home/fooadmin -m -g fooadmin -l fooadmin admin  # after renaming user
```

## see also

- [[useradd]]
- [[adduser]]
- [[groupadd]]
