---
tags: [linux, macos]
title: certutil
created: '2023-07-12T07:32:56.035Z'
modified: '2023-07-19T11:17:39.576Z'
---

# certutil

> manage keys and certificate in both NSS databases and other NSS tokens

## install

```sh
brew install nss
```

## usage

```sh
certutil -N -d [sql:]DIR   # create new db

certutil -R -k rsa -g 1024 \
  -s "CN=John Smith,O=Example Corp,L=Mountain View,ST=California,C=US" \
  -d sql:$HOME/nssdb -p 650-555-0123 -a -o cert.cer

certutil -S -s "CN=Example CA" -n my-ca-cert -x -t "C,C,C" -1 -2 -5 -m 3650   # self signed cert

certutil -S -s "CN=My Server Cert" -n my-server-cert -c "my-ca-cert" -t "u,u,u" -1 -5 -6 -8 -m 730
```

## see also

- [[openssl]]
- [[cosign]]
- [[mkcert]]
- [manpages.ubuntu.com/manpages/xenial/en/man1/certutil.1.html](https://manpages.ubuntu.com/manpages/xenial/en/man1/certutil.1.html)
- [www-archive.mozilla.org/projects/security/pki/nss/tools/certutil](https://www-archive.mozilla.org/projects/security/pki/nss/tools/certutil)
