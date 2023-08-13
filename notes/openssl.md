---
tags: [crypto, linux, network]
title: openssl
created: '2019-07-30T06:19:49.183Z'
modified: '2023-07-12T08:13:51.407Z'
---

# openssl

> `openssl` is a cryptography toolkit implementing the `ssl` and `tls` network protocols and related cryptography standards

## install

```sh
brew install openssl    # export PATH after
```

## usage

```sh
openssl version -help     # get version options
openssl version -a        # show all version data
openssl version -d        # configuration files and certificates location

openssl pkcs12 -in cert.p12 -clcerts -nokeys -out cert.crt

openssl x509   -in cert.crt -text -noout

openssl crl2pkcs7 -nocrl -certfile CHAIN.pem | openssl pkcs7 -print_certs -text -noout


openssl verify -CAfile foo.cain.crt foo.crt   # verify certificate against CAfile => foo.crt: OK
```

## rsa 

> rsa key management

```sh
openssl rsa -in privateKey.key -check

openssl rsa -in private_key_noenc.pem -out private_key_noenc.pem          # remove passphrase

openssl rsa -aes256 -in private_key_noenc.key -out private_key_enc.key    


# Verify that private key matches a certificate and CSR
openssl rsa  -noout -modulus -in example.key | openssl sha256
openssl x509 -noout -modulus -in example.crt | openssl sha256
openssl req  -noout -modulus -in example.csr | openssl sha256
```

## req - pkcs10 x509 

> certificate Signing Request (csr) management

```sh
# generate a self-signed certificate and key
openssl req -x509 -nodes -days 365 -sha256 -newkey rsa:2048 -keyout key.pem -out cert.pem
openssl req -x509 -nodes -days 365         -newkey rsa:2048 -keyout key.pem -out cert.pem

# auto-fill generate a self-signed certificate
openssl req -x509 -nodes -days 365 -sha256 -newkey rsa:2048 -keyout key.pem -out cert.pem
  -subj '/C=US/ST=Oregon/L=Portland/CN=www.foo.bar'

openssl req -x509 -newkey rsa:2048 -keyout local.key -out local.crt -days 90 \
  -subj '/C=US/ST=XX/L=XX/O=IT/OU=IT/CN=foohost.local/emailAddress=it@foohost.net'

# -nodes             don't encrypt the output key
# -x509              output a x509 structure instead of a cert. req
# -newkey rsa:bits   generate a new RSA key of 'bits' in size
# -newkey dsa:file   generate a new DSA key, parameters taken from CA in 'file'
# -newkey ec:file    generate a new EC  key, parameters taken from CA in 'file'
```

## read csr

```sh
openssl req -noout -text -in int-ca_intermediate.csr

openssl req -in mycsr.csr -noout -text
```

## x509 certificate data management

```sh
openssl x509 -in somecert{.crt,.pem} -text -noout             # certificate-information from file

openssl x509 -inform der -in aps.cer -noout -text
openssl x509 -in FILE.cert -noout -subject
openssl x509 -in FILE.cert -noout -dates
openssl x509 -in FILE.cert -noout -fingerprint
```

## pkcs12

> public key cryptograpy standarts

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

## s_client

> implements a generic `SSL/TLS` client which can establish a transparent connection to a remote server speaking SSL/TLS for testing

## usage
```sh
openssl s_client -connect google.com:443                  # test ssl connection
GET / HTTP/1.1
Host: www.google.com
# returns html
Q         # type Q and return
DONE


openssl s_client -connect localhost:443 -debug

openssl s_client -connect gateway.sandbox.push.apple.com:2195 -CAfile CA/entrust_2048_ca.cer -debug -showcerts  -cert newfile.pem

openssl s_client -connect b.com:443 -servername a.com   # multiple hosts on the same IP address and you need to use Server Name Indication (SNI) to access this site

echo | openssl s_client -connect www.bar.baz:443 -servername bar.baz 2>/dev/null | openssl x509 -noout -dates

echo | openssl s_client -connect bar.baz:443 2>&1 | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p'    # retrieve remote certificate

openssl s_client -connect example.com:25 -starttls smtp -showcerts </dev/null 2>/dev/null   \
  | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :

openssl s_client -connect example.com:587 -starttls smtp -showcerts </dev/null 2>/dev/null  \
  | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :

openssl s_client -connect example.com:143 -starttls imap -showcerts </dev/null 2>/dev/null  \
  | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :

openssl s_client -connect example.com:993 -showcerts </dev/null 2>/dev/null \
  | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :

echo | openssl s_client -connect google.test:443 2>&1 1>/dev/null
getaddrinfo: nodename nor servname provided, or not known
connect:errno=0

echo | openssl s_client -connect google.test:443 1>/dev/null 2>&1
```

### determin certificate type

- `X509` standard defines certificates
- `RSA` and `DSA` are two of the `public key algorithms` that can be used in those certificates
- certificates are used to hold public keys, and never private keys.
- `PKCS#12` is a standard for a container which can hold an `X509` client certificates and the corresponding private keys,
  - as well as (optionally) the `X509` certificates of the CAs that signed the `X509` client certificate(s).
- if you're examining a `PKCS#12` file (typically `.p12` extension), then you already know:
  - contains at least one `X509` client certificate (which contains a public key) and the corresponding private keys
  - All you don't know is whether those certificate & private key are `RSA` or `DSA`. You can check by extracting the certificate(s) and then examine them

## digest

> dgst - Message Digest Calculation

```sh
openssl md5 FILENAME
openssl sha1 FILENAME

openssl dgst -md5 FILENAME
openssl dgst -sha1 FILENAME
openssl dgst -sha256 FILENAME
```

[[md5sum]], [[sha256sum]]

## dhparam

> generate set of diffie-hellman parameters 
> consists of a large prime number `p` and  generator value `g` (which is always 2 for openssl)

```sh
openssl dhparam -out dhparam.pem 4096  # generates dh parameters with 4096 bit
```

[[prime number]]

## passwd

> generation of hashed passwords

```sh
openssl passwd MySecret      # generate hash: 8E4vqBR4UOYF.

openssl passwd -1 MySecret   # generate shadow-style-hash: $1$sXiKzkus$haDZ9JpVrRHBznY5OxB82.

# -crypt             standard Unix password algorithm (default)
```

[[pass]], [[openssl rand]]


## rand

> generate pseudo-random bytes and password

```sh
openssl rand -base64 32      # generate random numner
```

[[shuf]]


## see also

- [[gpg]]
- [[certutil]]
- [[mkcert]]
- [[keytool]]
- [[p11-kit]]
- [[keybase]]
- [[xkcdpass]]
- [megamorf.gitlab.io/cheat-sheets/openss/](https://megamorf.gitlab.io/cheat-sheets/openssl/)
- [blog.filippo.io/mkcert-valid-https-certificates-for-localhost](https://blog.filippo.io/mkcert-valid-https-certificates-for-localhost/)
- [madboa.com/geek/openssl/#how-do-i-get-a-list-of-the-available-commands](https://www.madboa.com/geek/openssl/#how-do-i-get-a-list-of-the-available-commands)
- [medium.freecodecamp.org/openssl-command-cheatsheet](https://medium.freecodecamp.org/openssl-command-cheatsheet-b441be1e8c4a)
- [cheat.readthedocs.io/en/latest/openssl](https://cheat.readthedocs.io/en/latest/openssl.html)
- [sslshopper.com/article-most-common-openssl-commands](https://www.sslshopper.com/article-most-common-openssl-commands.html)
- [How to determine certificate type from file - Stack Overflow](http://stackoverflow.com/questions/1722181/how-to-determine-certificate-type-from-file)
- [openssl -connect returns wrong certificate - Stack Overflow](http://stackoverflow.com/a/24615393)
- [Check SSL Certificate Expiration Date and More - ShellHacks](http://www.shellhacks.com/en/HowTo-Check-SSL-Certificate-Expiration-Date-from-the-Linux-Shell)
