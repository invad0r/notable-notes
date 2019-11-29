---
tags: [linux]
title: usermod
created: '2019-11-22T19:13:02.970Z'
modified: '2019-11-29T11:34:22.437Z'
---

# usermod

## usage

```sh
usermod -a -G GROUPNAME USERNAME          # -a    append

usermod -g PRIMARYGROUPNAME USERNAME      # -g    primary group assigned to the users

usermod -G SECONDARYGROUPNAME USERNAME    # -G    Other groups the user belongs to


# rename-user
groupadd fooadmin
usermod -d /home/fooadmin -m -g fooadmin -l fooadmin admin
```


## see also
- [[useradd]]
- [[groupadd]]
