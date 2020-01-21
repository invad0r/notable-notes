---
tags: [linux, network]
title: nc
created: '2019-07-30T06:19:49.181Z'
modified: '2020-01-20T08:26:02.804Z'
---

# nc

> `netcat`- arbitrary tcp/udp connections and listens

## install
`brew install netcat`, `apt install netcat`, `yum install netcat`

## usage
```sh
# options: 
# -h, --help                 display this help and exit
# -z                         scan for listening daemons, without sendin any data
# -v                         verbose output
# -i interval                delay time interval between lines of text sent and received
# -l                         listen for an incoming connection
# -p source_port             not used with -l
# -w timeout                 if connection/stdin are idle for more than timeout sec, then the connection is silently closed
# -e, --exec=PROGRAM         program to exec after connect
# -k                          


/usr/bin/nc -k -l 4444          # osx default
/usr/local/bin/nc -l -p 4444    # osx brew uses gnu-netcat; needs -p PORT !


nc -zv serverhost 27017                                             # check if port is open

nc -u -zv 192.168.100.1 80-200                                      # scan udb prots 80 to 200


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
```


## see also
- [[ncat]]
- [[socat]]
- [[tar]]
- [[gpg]]
- [[lzcat]]
- [Ship It with Netcat - The Blog of Tom Webster](https://samurailink3.com/blog/2013/12/31/ship-it-with-netcat/)
