---
tags: [linux, network, webserver]
title: nc
created: '2019-07-30T06:19:49.181Z'
modified: '2023-03-20T09:00:40.132Z'
---

# nc

> `netcat`- arbitrary tcp/udp connections and listens

## install

```sh
brew install netcat
apt  install netcat
yum  install netcat
```

## flag

```sh
-h, --help                 # display this help and exit
-z                         # scan for listening daemons, without sendin any data
-v                         # verbose output
-i interval                # delay time interval between lines of text sent and received
-l                         # listen for an incoming connection
-p source_port             # not used with -l
-w timeout                 # if connection/stdin are idle for more than timeout sec, then the connection is silently closed
-e, --exec=PROGRAM         # program to exec after connect
-k                         #  
```

## usage

```sh
/usr/bin/nc -k -l 4444          # osx default
/usr/local/bin/nc -l -p 4444    # osx brew uses gnu-netcat; needs -p PORT !


nc -zv serverhost 27017                                             # check if port is open

nc -u -zv 192.168.100.1 80-200                                      # scan udb prots 80 to 200


echo "PING" | nc 127.0.0.1 3310                       # sends ping

nc -l 5566 -e /bin/bash                                             # create a backdoor-shell
nc 192.168.100.1 5566                                               # use shell

nc -q1 -lvp 1234 < file.txt                                         # poor man's file server
nc serverhost 1234 > output.txt                                     # to retrieve file from remote host. NAT bugs this.

nc -l 1234 > out.file                                               # wait for receiving file
nc -w 30 serverhost 1234 < out.file                                 # send file over network, timeout after 30 sec

tar czvf - /path/to/directory | nc host-IP 4444                     # sending directory
nc -l 4444                    | tar xzvf -                          # receiving directory


tar c myproject/ | lzma \
  | gpg -a -c --cipher-algo AES256 --digest-algo SHA512 -o - \
  | nc -w 1 192.168.1.102 1337                                      # sending file encrypted
nc -lp 1337 | gpg -v -o - | lzcat | tar x -C /home/user/            # receiving file encrypted


while true; do sudo nc -lp 80 < index.html; done                    # web-server with a static page

printf "GET /nc.1 HTTP/1.1\r\nHost: man.openbsd.org\r\n\r\n" | nc man.openbsd.org 80  # get request
echo -ne "POST /-/reload HTTP/1.0r\nHost: localhostr\n" | nc -i localhost 8080        # post request

#!/bin/sh
echo "why am i like this"
while [ 1 ]; do 
  { 
    echo -ne "HTTP/1.1 200 OK\nContent-Type: text/html; 
    charset=UTF-8\nServer: netcat\n\n"; 
    cat index.md | ./wcgow; 
  } | nc -w 1 -l -N -p 8080; 
done


echo 'Hello, Seashells!' | nc seashells.io 1337     # "pipe output from command-line programs to the web in real-time"
```

## see also

- [[curl]]
- [[ncat]]
- [[socat]]
- [[netstat]]
- [[tar]]
- [[gpg]]
- [[lzcat]]
- [seashells.io](seashells.io)
- [samurailink3.com/blog/2013/12/31/ship-it-with-netcat](https://samurailink3.com/blog/2013/12/31/ship-it-with-netcat/)
- [[redis-cli]]
