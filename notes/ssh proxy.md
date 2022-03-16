---
tags: [ssh]
title: ssh proxy
created: '2019-07-30T06:19:49.242Z'
modified: '2022-01-31T19:00:58.542Z'
---

# ssh proxy

aka `pivoting`

## local port forwarding

```sh
ssh -L <lport>:<target-host>:<tport> <pivot host>

ssh -L 8080:localhost:80 daito
curl http://localhost:8080
```

## Remote/Revers Port Forward

forward port on `<pivot-host>`

```sh
ssh -R <rport>:<target-host>:<tport> <pivot-host>

# Host-A
# open ssh-session to a remote server Host-B
ssh -R 2222:localhost:22 daito

# Host-B
# from remote server connect back to Host-A
ssh root@localhost -p 2222
```

## Jump Host

```sh
ssh -J <jump-host> <target-host>


ssh -j r00k@jump1,r00k@jump2 rook@jump3

ssh -j r00k@jump1 -L 8080:jump3:80 rook@jump2
curl http://127.0.0.1:8080
```

## dynamic port forward

```sh
ssh -D <proxy port> <pivot-host>

ssh -J r00k@jump1 -D 8080 r00k@jump2
curl -x SOCKS5://localhost:8080 http://jump3
```

## see also

- [[socat]]
- [[ssh config]]
- [KringleCon - Derek Rook, Pivoting: SSH - YouTube](https://www.youtube.com/watch?v=f5uaxLjCkK0)
- [SSH Tunneling Magic – Reznok](https://reznok.com/ssh-tunneling-magic/)
- [Derek Rook / Pentest Process · GitLab](https://gitlab.com/r00k/pentest-process)
