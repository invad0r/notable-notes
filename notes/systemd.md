---
tags: [linux]
title: systemd
created: '2019-07-30T06:19:49.250Z'
modified: '2019-08-18T14:13:31.356Z'
---

# systemd

[What is the difference between service and systemctl? - Server Fault](https://serverfault.com/questions/867322/what-is-the-difference-between-service-and-systemctl)

```sh
systemctl list-unit-files --state=enabled

systemctl --type=service      # list current services

systemctl status

systemctl start

systemctl stop

systemctl restart
```


### output

using output from `journalctl`

```sh
systemctl --output=json status docker-volume-netshare.service

    # short
    # short-full
    # export
    # json
    # json-pretty
    # json-sse
    # json-seq
    # cat
    # with-unit
```
[systemd/man/journalctl#-o](https://www.freedesktop.org/software/systemd/man/journalctl#-o)

### property
```sh
systemctl show your.service     # get all properties

systemctl show docker-volume-netshare.service --property=ActiveState
```


## jounralctl

```sh
journalctl -f     # follow


journalctl -u ssh   # Show Logs for a systemd ServicePermalink


journalctl -k       # View Kernel MessagesPermalink
```


### Change the Log Output FormatPermalink

```sh
journalctl -o json-pretty
```


### Manually Clean Up Archived LogsPermalink

```sh
journalctl --vacuum-size=2G
```


[Use journalctl to View Your System's Logs](https://www.linode.com/docs/quick-answers/linux/how-to-use-journalctl/)
