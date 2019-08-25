---
tags: [initsystem, linux]
title: systemd jounralctl
created: '2019-08-19T09:11:28.583Z'
modified: '2019-08-22T07:22:31.103Z'
---

# systemd jounralctl

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
## see also
- [[systemd systemctl]]
- [Use journalctl to View Your System's Logs](https://www.linode.com/docs/quick-answers/linux/how-to-use-journalctl/)
- [systemd/man/journalctl](https://www.freedesktop.org/software/systemd/man/journalctl#-o)
