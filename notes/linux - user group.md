---
tags: [linux]
title: linux - user group
created: '2019-07-30T06:19:49.163Z'
modified: '2019-08-18T14:45:37.385Z'
---

# linux - user group

## add user and authorized-key
```sh
useradd -d /home/admin -G sudo,admin -m -s /bin/bash admin

mkdir /home/admin/.ssh/

cat > /home/admin/.ssh/authorized_keys <<!
ssh-rsa AAAAB3NzaC1yc..AsZXb1w==
!

chown admin: -R /home/admin

chmod -R 700 /home/admin/.ssh

cat > /etc/sudoers.d/foo <<!
%admin ALL=(ALL) NOPASSWD: ALL
!

chmod 440 /etc/sudoers.d/foo
```

## delete user
```sh
userdel -r foo   # removes user and home + email spool
```

## add-user-to-group

```sh
usermod -a -G <groupname> <username>      # -a (append)

usermod -g primarygroupname username      # -g (primary group assigned to the users)

usermod -G secondarygroupname username    # -G (Other groups the user belongs to)

# adm: Group adm is used for system monitoring tasks.
# Members of this group can read many log files in /var/log, and can use xconsole.
# Historically, /var/log was /usr/adm (and later /var/adm), thus the name of the group.
```
http://www.howtogeek.com/50787/add-a-user-to-a-group-or-second-group-on-linux/


# rename-user
```sh
groupadd fooadmin
usermod -d /home/fooadmin -m -g fooadmin -l fooadmin admin
```
http://unix.stackexchange.com/a/230426/193945


# change-user-id
```sh
usermod -u <NEWUID> <LOGIN>
groupmod -g <NEWGID> <GROUP>

find / -user <OLDUID> -exec chown -h <NEWUID> {} \;
find / -group <OLDGID> -exec chgrp -h <NEWGID> {} \;

usermod -g <NEWGID> <LOGIN>
```
https://muffinresearch.co.uk/linux-changing-uids-and-gids-for-user/



## set an impossible password for user
```sh
# usermod -p "*" kano
# grep kano /etc/shadow
kano:*:16280:7:60:7:::
```
http://arlimus.github.io/articles/usepam/

```sh
groupmod -g 5000 fooadmin     # change-group-id
gpasswd -d user group         # remove user from group
```
