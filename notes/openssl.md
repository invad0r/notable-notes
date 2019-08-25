---
tags: [encryption, linux, network]
title: openssl
created: '2019-07-30T06:19:49.183Z'
modified: '2019-08-20T09:47:48.676Z'
---

# openssl

- mkcert self-signed for localhost: [mkcert: valid HTTPS certificates for localhost](https://blog.filippo.io/mkcert-valid-https-certificates-for-localhost/)
- [OpenSSL CLI HowTo](https://www.madboa.com/geek/openssl/#how-do-i-get-a-list-of-the-available-commands)
- [OpenSSL command cheatsheet – freeCodeCamp.org](https://medium.freecodecamp.org/openssl-command-cheatsheet-b441be1e8c4a)
- [OpenSSL — Dan's Cheat Sheets 1 documentation](https://cheat.readthedocs.io/en/latest/openssl.html)
- [The Most Common OpenSSL Commands](https://www.sslshopper.com/article-most-common-openssl-commands.html)

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
openssl pkcs12 -in mycert.p12 -clcerts -nokeys -out mycert.crt
openssl x509   -in mycert.crt -text
```
[How to determine certificate type from file - Stack Overflow](http://stackoverflow.com/questions/1722181/how-to-determine-certificate-type-from-file)

### rand - generate pseudo-random bytes and password
```sh
openssl rand -base64 32      # generate random numner

openssl passwd MySecret      # generate hash: 8E4vqBR4UOYF.

openssl passwd -1 MySecret   # generate shadow-style-hash: $1$sXiKzkus$haDZ9JpVrRHBznY5OxB82.
```

### verify certificate against CAfile
```sh
openssl verify -CAfile foo.cain.crt foo.crt
foo.crt: OK
```


### s_client
```sh
openssl s_client -connect google.com:443                  # test ssl connection
GET / HTTP/1.1
Host: www.google.com
# returns html
Q         # type Q and return
DONE
```
```sh
openssl s_client -connect b.com:443 -servername a.com   # multiple hosts on the same IP address and you need to use Server Name Indication (SNI) to access this site

echo | openssl s_client -connect www.bar.baz:443 -servername bar.baz 2>/dev/null | openssl x509 -noout -dates

echo | openssl s_client -connect bar.baz:443 2>&1 | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p'    # retrieve remote certificate

openssl s_client -connect localhost:443 -debug
```
[openssl -connect returns wrong certificate - Stack Overflow](http://stackoverflow.com/a/24615393)
[Check SSL Certificate Expiration Date and More - ShellHacks](http://www.shellhacks.com/en/HowTo-Check-SSL-Certificate-Expiration-Date-from-the-Linux-Shell)

```sh
openssl s_client 
  -connect gateway.sandbox.push.apple.com:2195 
  -CAfile CA/entrust_2048_ca.cer 
  -debug
  -showcerts 
  -cert newfile.pem
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
---
### Certificate = Valication Level + Type


### Valication Level
- `EV` Extended Validation Certificates
- `OV` Organization Validated Certificates
- `DV` Domain Validated Certificates

### Type
- Single Domain Certificates
- Wildcard SSL Certificate
- `MDC` Multi Domain SSL Certificate used with SAN-Extension
- `UCC` Unified Communications Certificate used with SAN-Extension

[The Difference between Wildcard & Multi Domain (SAN) SSL Certificate](https://cheapsslsecurity.com/blog/the-difference-between-wildcard-and-multi-domain-san-ssl-certificate/)
[Types of SSL Certificate from InstantSSL | Comodo CA](https://www.instantssl.com/ssl-faqs/types-of-ssl-certificate.html)
[Difference Between Wildcard SSL Vs SAN Certificate - Hashed Out by The SSL Store™](https://www.thesslstore.com/blog/difference-between-wildcard-ssl-vs-san-certificate/)
