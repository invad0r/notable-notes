---
tags: [linux, network]
title: nc
created: '2019-07-30T06:19:49.181Z'
modified: '2019-08-20T09:47:25.538Z'
---

# nc

> `netcat`- arbitrary TCP/UDP connections and listens

```sh
-z              # scan for listening daemons, without sendin any data

-v              # verbose output

-w timeout      # if connection/stdin are idle for more than timeout sec, then the connection is silently closed

-l              # listen for an incoming connection

-p source_port  # not used with -l

-i interval     # delay time interval between lines of text sent and received
```

## check if port is open
```sh
nc -zv foo.bar.com 27017  
nc -zv 10.32.23.30 2376
```


### send file over network
```sh
nc -l 1234 > out.file                     # wait for receiving file

nc -w 30 [destination] 1234 < out.file    # send file
```

### send file over network encrypted
```sh
# sending
tar c myproject/ | lzma | gpg -a -c --cipher-algo AES256 --digest-algo SHA512 -o - | nc -w 1 192.168.1.102 1337

# receivinb
nc -lp 1337 | gpg -v -o - | lzcat | tar x -C /home/user/
```
[Ship It with Netcat - The Blog of Tom Webster](https://samurailink3.com/blog/2013/12/31/ship-it-with-netcat/)


## send post request
```sh
echo -ne "POST /-/reload HTTP/1.0r\nHost: localhostr\n" | nc -i localhost 8080

curl -X POST http://localhost:8080/-/reload
```
