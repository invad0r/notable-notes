---
tags: [ssh]
title: ssh
created: '2019-07-30T06:19:49.245Z'
modified: '2021-06-04T12:20:12.892Z'
---

# ssh
> `secure shell`

## usage
```sh
SSH_ASKPASS               # set by ssh user   - path to askpass program
SSH_AUTH_SOCK             # set by ssh-agent  - path to socket
SSH_CLIENT                # set by sshd       - client socket info like ip from which you connected to host
SSH_CONNECTION            # set by sshd       - client and server socket info
SSH_ORIGINAL_COMMAND      # set by sshd       - client’s remote command string
SSH_TTY                   # set by sshd       - name of allocated tty
```
```sh
-n    #  redirects STDIN from /dev/null which prevents reading from STDIN, used inside loops
-l    #  specify username for login
-o ServerAliveInterval=60 -o ServerAliveCountMax=120   # 120 x 60
-o StrictHostKeyChecking=no
-o StrictHostKeyChecking=accept-new
-o LogLevel=LOGLEVEL                    # loglevels: QUIET, FATAL, ERROR, INFO, VERBOSE, DEBUG, DEBUG1, DEBUG2, and DEBUG3
-o CheckHostIP=no
-o HostKeyAlias=ALIAS
-o IdentitiesOnly=yes 
-o UserKnownHostsFile=/PATH/TO/.ssh/known_hosts 
-o PreferredAuthentications=password
-o PubkeyAuthentication=no
```
```sh
ssh whoami.filippo.io           # prints _o/ Hello! and closes

ssh -T git@github.com           # test ssh-connection

ssh -t                          # Force pseudo-terminal allocation.

ssh -i /Users/user/.ssh/gce     # use different identity file

ssh -p PORT user@host           # connects specified port

ssh -n user@host 'uptime'       # don't read from stdin, e.g. in a loop

ssh -C                          # compress all data stdin, stdout, stderr, x11, tpc, unix-domain-connections via gzip
```

## see also
- for session recon/system info use: [[uptime]], [[id]], [[w]], [[uname]], [[passwd]], [[quota]], [[date]], [[cal]], [[finger]], [[last]], [[bash history]]
- [[git]]
- [[sshpass]]
- [[last]]
- [[tty]]
- [[rsync]]
- [Connecting to GitHub with SSH - User Documentation](https://help.github.com/articles/connecting-to-github-with-ssh/)
- [ssh_config(5) - LogLevel](http://man.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man5/ssh_config.5?query=ssh_config#LogLevel)
- [Shell script while read line loop stops after the first line - Stack Overflow](https://stackoverflow.com/a/13800476)
- [ssh - How to fix warning about ECDSA host key - Super User](https://superuser.com/a/421024/341187)
