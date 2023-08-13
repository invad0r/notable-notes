---
tags: [crypto, go]
title: mkcert
created: '2023-07-11T11:08:25.241Z'
modified: '2023-07-12T07:32:53.565Z'
---

# mkcert

> generate locally-trusted development certificates

## install

```sh
brew install mkcert
```
## env

```sh
TRUST_STORES
```

## usage

```sh
mkcert -install                                             # install local CA in system trust store
mkcert -uninstall                                           # uninstall local CA (don't delete it)

mkcert example.org                                          # generate "example.org.pem" and "example.org-key.pem"
mkcert example.com myapp.dev localhost 127.0.0.1 ::1        # generate "example.com+4.pem" and "example.com+4-key.pem"
mkcert "*.example.it"                                       # generate "_wildcard.example.it.pem" and "_wildcard.example.it-key.pem"
```

## see also

- [[certutil]]
- [[openssl]]
- [github.com/FiloSottile/mkcert](https://github.com/FiloSottile/mkcert)
