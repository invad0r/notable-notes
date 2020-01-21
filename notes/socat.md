---
tags: [linux, network]
title: socat
created: '2019-07-30T06:19:49.239Z'
modified: '2020-01-21T07:27:30.449Z'
---

# socat

>  multipurpose relay - `SOcket CAT`

## install
`brew install socat`, `apt install socat`, `yum install socat`

## usage
```sh
socat INPUT_TYPE(OPTIONS) OUTPUT_TYPE(OPTIONS)


socat SYSTEM:ls -                                             # print system-command to stdout

socat STDIO FILE:/home/user/test,create                       # read from stdin and write to file

socat FILE:/tmp/test1 FILE:/tmp/test:append


socat - TCP:poftut.com:www,crnl                               # surf web over stdin


socat UDP-LISTEN:8888 -               # listen and print to stdout
socat UDP:localhost:8888 -

socat tcp­-listen:9999,reuseaddr -    # allow other sockets to bind to address even if parts of it are in use
socat ­-x tcp:localhost:9999 -        #  write transferred also to stderr in hexadecimal format


socat TCP4-LISTEN:1234,reuseaddr,fork gopen:/home/user/capture,seek-end=,append

socat TCP-LISTEN:80,fork TCP:202.54.1.5:80                    # redirect all port 80 conenctions to ip 202.54.1.5

echo "show info" | socat unix-connect:/var/tmp/haproxy stdio  # information about the running HAProxy

socat -d -d -lmlocal2 \
  TCP4-LISTEN:80,bind=myaddr1,su=nobody,fork,range=10.0.0.0/8,reuseaddr \
  TCP4:www.nixcraft.net.in:80,bind=myaddr2
```

## see also
- [socat – Cindy Sridharan – Medium](https://medium.com/@copyconstruct/socat-29453e9fc8a6)
- [[unix socket]]
- [[nmap]]
- [[ncat]]
