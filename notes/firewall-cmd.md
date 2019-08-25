---
tags: [linux]
title: firewall-cmd
created: '2019-08-23T13:34:33.074Z'
modified: '2019-08-23T13:52:51.428Z'
---

# firewall-cmd

```sh
firewall-cmd --state

systemctl status firewalld


firewall-cmd --list-all     # print the whole Firewalld configuration


firewall-cmd --list-all-zones

firewall-cmd --get-default-zone

firewall-cmd --list-services
```


## add port
```sh
firewall-cmd --zone=public --add-port=9002/tcp

firewall-cmd --runtime-to-permanent   # copy the running configuration to the permanent configuration

firewall-cmd --reload
```

 ## see also
 - [[firewalld]]
