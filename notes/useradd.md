---
tags: [linux]
title: useradd
created: '2019-07-30T06:19:49.163Z'
modified: '2019-11-22T19:24:56.512Z'
---

# useradd

## usage
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

# change-user-id
```sh
usermod -u <NEWUID> <LOGIN>
groupmod -g <NEWGID> <GROUP>

find / -user <OLDUID> -exec chown -h <NEWUID> {} \;
find / -group <OLDGID> -exec chgrp -h <NEWGID> {} \;

usermod -g <NEWGID> <LOGIN>
```

```sh
groupmod -g 5000 fooadmin     # change-group-id
gpasswd -d user group         # remove user from group
```

## see also
- [add-a-user-to-a-group-or-second-group-on-linux](http://www.howtogeek.com/50787/add-a-user-to-a-group-or-second-group-on-linux/)
- [linux-changing-uids-and-gids-for-user/](https://muffinresearch.co.uk/linux-changing-uids-and-gids-for-user/)
- [articles/usepam/ SSH and locked users](http://arlimus.github.io/articles/usepam/)
