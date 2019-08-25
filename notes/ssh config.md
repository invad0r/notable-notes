---
tags: [ssh]
title: ssh config
created: '2019-08-22T08:32:53.895Z'
modified: '2019-08-22T11:07:42.184Z'
---

# ssh config

```
man ssh_config
```

## `~/.ssh/config` entries
```sh 
Host                    # Defines host or hosts to which the configuration section applies. 
                        # The section ends with a new Host section or the end of the file. 
                        # A single * as a pattern can be used to provide global defaults for all hosts.

Host * !martell         # all hosts except martell
```

```sh
HostName                # real host name to log into,n umeric IP addresses are also permitted.

User                    # username for connection

IdentityFile            # Specifies a file from which the user’s DSA, ECDSA or DSA authentication identity is read. 
                        # defaults:
                        #   protocol version 1: ~/.ssh/identity
                        #   protocol version 2: ~/.ssh/id_dsa, ~/.ssh/id_ecdsa and ~/.ssh/id_rsa

ProxyCommand            # specifies command to use to connect to the server,  placeholders (%h) will be substituted.
                        # command can be basically anything, and should read from its standard input and write to its standard output. 
                        # useful in conjunction with nc and its proxy support. e.g. connect via an HTTP proxy at 192.1.0.253: 
                        #     ProxyCommand /usr/bin/nc -X connect -x 192.1.0.253:3128 %h %p

LocalForward            # Specifies that a local tcp-port to be forwarded over the secure channel to the specified host and port from the remote machine.
                        # The first argument must be [bind_address:]port and the second argument must be host:hostport.

Port                    # port to connect on the remote host

Protocol                # possible values: '1', '2'

ServerAliveInterval     # timeout interval in seconds after which if no data has been received from the server
                        # will send a message through the encrypted channel to request a response from the server

ServerAliveCountMax     # Sets the number of server alive messages which may be sent without receiving any messages back from the server
                        # If threshold is reached while server alive messages are being sent, ssh will disconnect from the server

ProxyJump               #


LogLevel                # INFO

Compression             # yes
```

## placeholders

> HostName accepts the tokens `%%` and `%h`

```sh
Host service-1 service-2
  HostName %h.foo.bar
  User root

#   %h - host name
#   %p - port
#   %r - remote user name
```

## proxy
```sh
Host foo
   HostName   %h.host.com
   ProxyJump  root@jumphost.net
   User       root
```

## see also
- [[sshd]]
- [create-ssh-config-file-on-linux-unix - cyberciti.biz](https://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/)
- [what does h mean in sshd configuration - askubuntu.com](https://askubuntu.com/questions/605479/what-does-h-mean-in-sshd-configuration)
- [Proxies_and_Jump_Hosts - wikikbooks.org](https://en.wikibooks.org/wiki/OpenSSH/Cookbook/Proxies_and_Jump_Hosts)
