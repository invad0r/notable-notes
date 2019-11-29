---
tags: [initsystem, linux, systemd]
title: systemd unit
created: '2019-08-20T06:14:13.706Z'
modified: '2019-08-27T07:14:56.501Z'
---

# systemd unit
> `Units` are the objects that `systemd` knows how to manage. A standardized representation of system resources that can be managed.

## paths
```sh
/usr/lib/systemd/systemd-logind

/lib/systemd/system     # sysetms copy of unit-files, default for installed unit files

/ect/systemd/system     # files here take precedence over other unit-files

/run/systemd/system     # run-time unit definition
```

## unit types
| type          | description |
|--             |--           |
| `.service`    | service on the system, including instructions for starting, restarting, and stopping the service |
| `.socket`     | network or IPC socket, or FIFO-buffer |
| `.device`     |  |
| `.mount`      |  |
| `.automount`  | mountpoint automatically mounted on boot |
| `.swap`       |  |
| `.target`     | synchronization point for other units. Usually used to start enabled services on boot. |
| `.path`       | for path-based activation. e.g. start services based on the state of a path, whether it exists or not |
| `.timer`      | schedule activation of another unit |
| `.snapshot`   | created via `systemctl snapshot` for reconstruction/roll-back state |
| `.slice`      | a unit assoc. with `cgroup` tree |
| `.scope`      | Information from systemd bus interfaces. Usually used to manage external system processes |

## see also
- [understanding-systemd-units-and-unit-files - digitalocean](https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files)
