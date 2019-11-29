---
tags: [cryptography, linux, network]
title: openssl
created: '2019-07-30T06:19:49.183Z'
modified: '2019-11-13T06:39:40.603Z'
---

# openssl

> `openssl` is a cryptography toolkit implementing the `ssl` and `tls` network protocols and related cryptography standards

### determin certificate type
- `X509` standard defines certificates
- `RSA` and `DSA` are two of the `public key algorithms` that can be used in those certificates
- certificates are used to hold public keys, and never private keys.
- `PKCS#12` is a standard for a container which can hold an `X509` client certificates and the corresponding private keys,
  - as well as (optionally) the `X509` certificates of the CAs that signed the `X509` client certificate(s).
- if you're examining a `PKCS#12` file (typically `.p12` extension), then you already know:
  - contains at least one `X509` client certificate (which contains a public key) and the corresponding private keys
  - All you don't know is whether those certificate & private key are `RSA` or `DSA`. You can check by extracting the certificate(s) and then examine them

```sh
openssl pkcs12 -in CERT.p12 -clcerts -nokeys -out CERT.crt

openssl x509   -in CERT.crt -text

openssl crl2pkcs7 -nocrl -certfile CHAIN.pem | openssl pkcs7 -print_certs -text -noout
```

### verify certificate against CAfile
```sh
openssl verify -CAfile foo.cain.crt foo.crt
foo.crt: OK
```


### rsa - RSA key management
```sh
openssl rsa -in privateKey.key -check

openssl rsa -in private_key_noenc.pem -out private_key_noenc.pem          # remove passphrase

openssl rsa -aes256 -in private_key_noenc.key -out private_key_enc.key    
```

### req - pkcs10 x509 - certificate Signing Request (csr) management
```sh
# generate a self-signed certificate
openssl req -x509 -nodes -days 365 -sha256 -newkey rsa:2048 -keyout mycert.pem -out mycert.pem    

# generate a self-signed certificate auto-fill
openssl req \
  -x509 \
  -nodes \
  -days 365 \
  -sha256 \
  -subj '/C=US/ST=Oregon/L=Portland/CN=www.foo.bar' \
  -newkey rsa:2048 \
  -keyout mycert.pem \
  -out mycert.pem

openssl req \
  -x509 \
  -newkey rsa:2048 \
  -keyout local.key \
  -out local.crt \
  -days 90 \
  -subj '/C=US/ST=XX/L=XX/O=IT/OU=IT/CN=foohost.local/emailAddress=it@foohost.net'

openssl req -nodes -newkey rsa:2048 -keyout www_domain_net.key -out www_domain_net.csr

# -nodes             don't encrypt the output key
# -x509              output a x509 structure instead of a cert. req
# -newkey rsa:bits   generate a new RSA key of 'bits' in size
# -newkey dsa:file   generate a new DSA key, parameters taken from CA in 'file'
# -newkey ec:file    generate a new EC  key, parameters taken from CA in 'file'
```

### read csr
```sh
openssl req -noout -text -in int-ca_intermediate.csr

openssl req -in mycsr.csr -noout -text
```

### x509 certificate data management
```sh
openssl x509 -in somecert{.crt,.pem} -text -noout             # certificate-information from file

openssl x509 -inform der -in aps.cer -noout -text

openssl x509 -in git.domain.net.crt -noout -subject

openssl x509 -in git.domain.net.crt -noout -dates

openssl x509 -in git.domain.net.crt -noout -fingerprint
```

## pkcs12 - public key cryptograpy standarts
```sh
openssl pkcs12 -export -inkey local.key      -in local.crt  -out local.pfx          # generate pkcs12
openssl pkcs12 -export -inkey privateKey.key -in bundle.crt -out certificate.pfx

openssl pkcs12 -info -in file.p12   # show cert and key
openssl pkcs12 -nokeys  -info -in file.p12 -passin pass:1234             # show only certificate
openssl pkcs12 -nocerts -info -in file.p12 -passin pass:1234             # show only certificate

openssl pkcs12 -export -in clientprivcert.pem -out clientprivcert.pfx     # convert PEM to PKCS12

openssl pkcs12 -in path.p12 -out newfile.crt.pem -nokeys  -clcerts    # extract certificate
openssl pkcs12 -in path.p12 -out newfile.key.pem -nocerts -nodes      # extract key 
```


## Verify that private key matches a certificate and CSR
```sh
openssl rsa  -noout -modulus -in example.key | openssl sha256
openssl x509 -noout -modulus -in example.crt | openssl sha256
openssl req  -noout -modulus -in example.csr | openssl sha256
```

## see also
- [[keytool]]
- [mkcert: valid HTTPS certificates for localhost](https://blog.filippo.io/mkcert-valid-https-certificates-for-localhost/)
- [OpenSSL CLI HowTo](https://www.madboa.com/geek/openssl/#how-do-i-get-a-list-of-the-available-commands)
- [OpenSSL command cheatsheet – freeCodeCamp.org](https://medium.freecodecamp.org/openssl-command-cheatsheet-b441be1e8c4a)
- [OpenSSL — Dan's Cheat Sheets 1 documentation](https://cheat.readthedocs.io/en/latest/openssl.html)
- [The Most Common OpenSSL Commands](https://www.sslshopper.com/article-most-common-openssl-commands.html)
- [How to determine certificate type from file - Stack Overflow](http://stackoverflow.com/questions/1722181/how-to-determine-certificate-type-from-file)
- [openssl -connect returns wrong certificate - Stack Overflow](http://stackoverflow.com/a/24615393)
- [Check SSL Certificate Expiration Date and More - ShellHacks](http://www.shellhacks.com/en/HowTo-Check-SSL-Certificate-Expiration-Date-from-the-Linux-Shell)

