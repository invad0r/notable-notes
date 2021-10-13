---
deleted: true
tags: [cryptography]
title: openssl s_client
created: '2019-10-11T06:30:33.271Z'
modified: '2021-10-11T09:22:40.294Z'
---

# openssl s_client

> implements a generic `SSL/TLS` client which can establish a transparent connection to a remote server speaking SSL/TLS for testing

## usage
```sh
openssl s_client -connect google.com:443                  # test ssl connection
GET / HTTP/1.1
Host: www.google.com
# returns html
Q         # type Q and return
DONE


openssl s_client -connect b.com:443 -servername a.com   # multiple hosts on the same IP address and you need to use Server Name Indication (SNI) to access this site

echo | openssl s_client -connect www.bar.baz:443 -servername bar.baz 2>/dev/null | openssl x509 -noout -dates

echo | openssl s_client -connect bar.baz:443 2>&1 | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p'    # retrieve remote certificate

openssl s_client -connect localhost:443 -debug

openssl s_client -connect gateway.sandbox.push.apple.com:2195 -CAfile CA/entrust_2048_ca.cer -debug -showcerts  -cert newfile.pem
```

## see also
- [[openssl]]
