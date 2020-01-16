---
tags: [linux, network]
title: nc
created: '2019-07-30T06:19:49.181Z'
modified: '2020-01-16T07:55:26.807Z'
---

# nc

> `netcat`- arbitrary TCP/UDP connections and listens

## install
`yum install nc`

## usage
```sh
nc -zv foo.bar.com 27017      # check if port is open

nc -zv 10.32.23.30 2376       # check if port is open

#  -z                 scan for listening daemons, without sendin any data
#  -v                 verbose output
#  -w timeout         if connection/stdin are idle for more than timeout sec, then the connection is silently closed
#  -l                 listen for an incoming connection
#  -p source_port     not used with -l
#  -i interval        delay time interval between lines of text sent and received


echo -ne "POST /-/reload HTTP/1.0r\nHost: localhostr\n" | nc -i localhost 8080    # send post request
# same as: curl -X POST http://localhost:8080/-/reload


# send file over network
nc -l 1234 > out.file                     # wait for receiving file

nc -w 30 [destination] 1234 < out.file    # send file


# send file over network encrypted
tar c myproject/ | lzma | gpg -a -c --cipher-algo AES256 --digest-algo SHA512 -o - | nc -w 1 192.168.1.102 1337   # sending

nc -lp 1337 | gpg -v -o - | lzcat | tar x -C /home/user/      # receiving



# poor man's file server
nc -q1 -lvp 1234 < file.txt         # Use 
nc serverhost 1234 > output.txt     # to retrieve file from remote host. NAT bugs this.
```


## see also
- [[tar]]
- [[gpg]]
- [Ship It with Netcat - The Blog of Tom Webster](https://samurailink3.com/blog/2013/12/31/ship-it-with-netcat/)
