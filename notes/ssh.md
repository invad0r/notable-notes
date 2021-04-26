---
tags: [ssh]
title: ssh
created: '2019-07-30T06:19:49.245Z'
modified: '2021-04-02T14:06:41.116Z'
---

# ssh
> `secure shell`

## usage
```sh
# options
-o ServerAliveInterval=60 -o ServerAliveCountMax=120   # 120 x 60
-o StrictHostKeyChecking=no
-o StrictHostKeyChecking=accept-new
-o LogLevel=LOGLEVEL    # LOGLEVEL: QUIET, FATAL, ERROR, INFO, VERBOSE, DEBUG, DEBUG1, DEBUG2, and DEBUG3
-o CheckHostIP=no
-o HostKeyAlias=compute.1407099891930101147 
-o IdentitiesOnly=yes 
-o UserKnownHostsFile=/Users/user/.ssh/google_compute_known_hosts 
-o PreferredAuthentications=password
-o PubkeyAuthentication=no

# -n    redirects STDIN from /dev/null which prevents reading from STDIN, used inside loops
# -l    specify username for login

# veriables
$SSH_CLIENT           # get ip from which you connected to host
$SSH_CONNECTION
$SSH_TTY



ssh whoami.filippo.io           # harmless

ssh -T git@github.com           # test ssh-connection

ssh -t                          # Force pseudo-terminal allocation.

ssh -i /Users/user/.ssh/gce     # use different identity file

ssh -p PORT user@host           # connects specified port

ssh -n user@host 'uptime'       # don't read from stdin, e.g. in a loop

ssh -C                          # compress all data stdin, stdout, stderr, x11, tpc, unix-domain-connections via gzip
```

## session recon/system info
```sh
uptime                   # shows current uptime
w                        # displays whois online
id
uname -a                 # shows kernel information
passwd                   # lets you change your password
quota -v                 # shows what your disk quota is
date                     # shows the current date and time
cal                      # shows the month's calendar
finger USER              # displays information about user
last USER                # lists your last logins
history
```

## see also
- [[sshpass]]
- [[last]]
- [[tty]]
- [[rsync]]
- [Connecting to GitHub with SSH - User Documentation](https://help.github.com/articles/connecting-to-github-with-ssh/)
- [ssh_config(5) - LogLevel](http://man.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man5/ssh_config.5?query=ssh_config#LogLevel)
- [Shell script while read line loop stops after the first line - Stack Overflow](https://stackoverflow.com/a/13800476)
- [ssh - How to fix warning about ECDSA host key - Super User](https://superuser.com/a/421024/341187)
