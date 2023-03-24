---
tags: [linux, systemd]
title: journalctl
created: '2019-08-19T09:11:28.583Z'
modified: '2023-03-23T08:40:13.237Z'
---

# journalctl

## usage

```sh
journalctl -f                   # follow

journalctl -u ssh               # Show Logs for a systemd ServicePermalink

journalctl -k                   # View Kernel MessagesPermalink

journalctl -o json-pretty       # Change the Log Output FormatPermalink

journalctl --vacuum-size=2G     # Manually Clean Up Archived LogsPermalink


journalctl -xefu SERVICE
```

## see also

- [[systemctl]]
- [[syslog]]
- [Use journalctl to View Your System's Logs](https://www.linode.com/docs/quick-answers/linux/how-to-use-journalctl/)
- [systemd/man/journalctl](https://www.freedesktop.org/software/systemd/man/journalctl#-o)
