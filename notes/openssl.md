---
tags: [cryptography, linux, network]
title: openssl
created: '2019-07-30T06:19:49.183Z'
modified: '2022-11-29T08:24:44.477Z'
---

# openssl

> `openssl` is a cryptography toolkit implementing the `ssl` and `tls` network protocols and related cryptography standards

- `x509` standard defines certificates
- `RSA` and `DSA` are two of the `public key algorithms` that can be used in those certificates
- certificates are used to hold public keys, and never private keys.
- `PKCS#12` is a standard for a container which can hold an `X509` client certificates and the corresponding private keys,
  - as well as (optionally) the `X509` certificates of the CAs that signed the `X509` client certificate(s).
- if you're examining a `PKCS#12` file (typically `.p12` extension), then you already know:
  - contains at least one `X509` client certificate (which contains a public key) and the corresponding private keys
  - All you don't know is whether those certificate & private key are `RSA` or `DSA`. You can check by extracting the certificate(s) and then examine them

## usage

```sh
openssl version -help     # get version options
openssl version -a        # show all version data
openssl version -d        # configuration files and certificates location

openssl verify -CAfile foo.cain.crt foo.crt   # verify certificate against CAfile => foo.crt: OK

# Verify that private key matches a certificate and CSR
openssl rsa  -noout -modulus -in example.key | openssl sha256
openssl x509 -noout -modulus -in example.crt | openssl sha256
openssl req  -noout -modulus -in example.csr | openssl sha256
```

## rsa 

> rsa key management

```sh
openssl rsa -in privateKey.key -check

openssl rsa -in private_key_noenc.pem -out private_key_noenc.pem          # remove passphrase

openssl rsa -aes256 -in private_key_noenc.key -out private_key_enc.key    
```

## x509 

> certificate data management

```sh
openssl x509   -in cert.crt -text -noout
openssl x509 -in somecert{.crt,.pem} -text -noout             # certificate-information from file
openssl x509 -inform der -in aps.cer -noout -text
openssl x509 -in git.domain.net.crt -noout -subject
openssl x509 -in git.domain.net.crt -noout -dates
openssl x509 -in git.domain.net.crt -noout -fingerprint
```

## req

> creates and processes certificate requests in PKCS#10 format, can create self-signed certificates, for use as root CAs

```sh
-nodes             # don't encrypt the output key
-x509              # output a x509 structure instead of a cert. req
-newkey rsa:bits   # generate a new RSA key of 'bits' in size
-newkey dsa:file   # generate a new DSA key, parameters taken from CA in 'file'
-newkey ec:file    # generate a new EC  key, parameters taken from CA in 'file'


openssl req -noout -text -in int-ca_intermediate.csr    # read cert signing

openssl req -in mycsr.csr -noout -text

# req - pkcs10 x509 - certificate Signing Request (csr) management
# generate a self-signed certificate and key
openssl req -x509 -nodes -days 365 -sha256 -newkey rsa:2048 -keyout key.pem -out cert.pem
openssl req -x509 -nodes -days 365         -newkey rsa:2048 -keyout key.pem -out cert.pem

# auto-fill generate a self-signed certificate
openssl req -x509 -nodes -days 365 -sha256 -newkey rsa:2048 -keyout key.pem -out cert.pem
  -subj '/C=US/ST=Oregon/L=Portland/CN=www.foo.bar'

openssl req -x509        -days 90          -newkey rsa:2048 -keyout local.key -out local.crt \
  -subj '/C=US/ST=XX/L=XX/O=IT/OU=IT/CN=foohost.local/emailAddress=it@foohost.net'
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

openssl pkcs12 -in cert.p12 -clcerts -nokeys -out cert.crt
```

## crl2pkcs7

> create a PKCS#7 structure from a CRL and certificates

```sh
-certfile FILE        # add certificates in PEM FILE to the PKCS#7 structure. can be used more than once to read certificates from multiple FILEs
-in FILE              # read the CRL from FILE, or STDIN if not specified
-inform FORMAT        # input format: der, pem 
-nocrl                # Normally, a CRL is included in the output FILE.  With this option, no CRL is included in the output FILE and a CRL is not read from the input FILE
-out FILE             # Write the PKCS#7 structure to file, or standard output if not specified
-outform FORMAT       # output format: der, pem 

openssl crl2pkcs7 -nocrl -certfile CERT_BUNDLE | openssl pkcs7 -print_certs -text -noout    # read multiple certificats from bundle

openssl crl2pkcs7 -nocrl -certfile CHAIN.pem | openssl pkcs7 -print_certs -text -noout
```

## s_client

> implements a generic `SSL/TLS` client which can establish a transparent connection to a remote server speaking SSL/TLS for testing

```sh
-4, -6                  # attempt connections using IPv4 or IPv6 only
-bugs                   # enable various workarounds for buggy implementations
-CAfile file            # A file containing trusted certificates to use during server authentication and to use when attempting to build the client certificate chain
-CApath directory       # directory to use for server certificate verification
-cert file              # certificate to use, if one is requested by the server. default is not to use a certificate
-cipher LIST            # modify cipher list sent by the client
-connect HOST:PORT      # host and port to connect to
-crlf                   # Translate a line feed from the terminal into CR+LF, as required by some servers
-debug                  # print extensive debugging information, including a hex dump of all traffic
-groups ecgroups        # Specify a colon-separated list of permitted EC curve groups
-ign_eof                # Inhibit shutting down the connection when end of file is reached in the input
-key keyfile            # The private key to use.  If not specified, the certificate file will be used
-msg                    # Show all protocol messages with hex dump
-nbio                   # Turn on non-blocking I/O
-nbio_test              # Test non-blocking I/O
-no_ticket              # Disable RFC 4507 session ticket support
-no_tls1                # disable tls v1  
-no_tls1_1              # disable tls v1.1
-no_tls1_2              # disable tls v1.2
-tls1                   # permit only tls v1.0
-tls1_1                 # permit only tls v1.1
-tls1_2                 # permit only tls v1.2
-pause                  # pause 1 second between each read and write call
-prexit                 # print session information when the program exits
-proxy HOST:PORT        # Use the HTTP proxy at host and port
-psk key                # Use the PSK key key when using a PSK cipher suite. The key is given as a hexadecimal number without the leading 0x, for example -psk 1a2b3c4d
-psk_identity identity  # use the PSK identity when using a PSK cipher suite
-quiet                  # Inhibit printing of session and certificate information, implicitly turns on -ign_eof as well
-reconnect              # Reconnect to the same server 5 times using the same session ID; this can be used as a test that session caching is working
-servername name        # Include the TLS Server Name Indication (SNI) extension in the ClientHello message, using the specified server name
-showcerts              # Display the whole server certificate chain: normally only the server certificate itself is displayed
-starttls protocol      # Send the protocol-specific messages to switch to TLS for communication.  protocol is a keyword for the intended protocol.  Currently, the supported keywords are "ftp", "imap", "smtp", "pop3", and "xmpp"
-state                  # Print the SSL session states
-tlsextdebug            # Print a hex dump of any TLS extensions received from the server
-verify depth           # turn on server certificate verification
-xmpphost hostname      # when used with -starttls xmpp, specify the host for the "to" attribute of the stream element.  If this option is not specified then the host specified with -connect will be used

openssl s_client -connect gateway.sandbox.push.apple.com:2195 -CAfile CA/entrust_2048_ca.cer -debug -showcerts  -cert newfile.pem

openssl s_client -connect URL_A:443 -servername URL_B   # multiple hosts on the same IP address and you need to use Server Name Indication (SNI) to access this site
openssl s_client -connect URL:443 -servername URL </dev/null 2>/dev/null | openssl x509 -noout -dates
openssl s_client -connect URL:443 </dev/null 2>&1 | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p'    # retrieve remote certificate

openssl s_client -connect localhost:443 -debug
openssl s_client -connect URL:443 -servername URL -showcerts </dev/null | openssl x509 -text
openssl s_client -connect URL:25  -starttls smtp  -showcerts </dev/null 2>/dev/null | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :
openssl s_client -connect URL:587 -starttls smtp  -showcerts </dev/null 2>/dev/null | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :
openssl s_client -connect URL:143 -starttls imap  -showcerts </dev/null 2>/dev/null | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :
openssl s_client -connect URL:993                 -showcerts </dev/null 2>/dev/null | openssl x509 -text -noout | grep -A 1 Serial\ Number | tr -d :

echo | openssl s_client -connect URL:443 2>&1 1>/dev/null

openssl s_client -connect google.com:443                  # test ssl connection
GET / HTTP/1.1
Host: www.google.com
          # returns html
Q         # type Q and return
DONE
```

## s_server

> implements a generic SSL/TLS server which listens for connections on a given port using SSL/TLS

```sh
openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365 -nodes # pre-requesite
openssl s_server -key key.pem -cert cert.pem -accept 44330 -www                   # start server
```

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

- [[mkcert]]
- [[gpg]]
- [[keytool]]
- [[p11-kit]]
- [[keybase]]
- [megamorf.gitlab.io/cheat-sheets/openss/](https://megamorf.gitlab.io/cheat-sheets/openssl/)
- [blog.filippo.io/mkcert-valid-https-certificates-for-localhost](https://blog.filippo.io/mkcert-valid-https-certificates-for-localhost/)
- [madboa.com/geek/openssl/#how-do-i-get-a-list-of-the-available-commands](https://www.madboa.com/geek/openssl/#how-do-i-get-a-list-of-the-available-commands)
- [medium.freecodecamp.org/openssl-command-cheatsheet](https://medium.freecodecamp.org/openssl-command-cheatsheet-b441be1e8c4a)
- [cheat.readthedocs.io/en/latest/openssl](https://cheat.readthedocs.io/en/latest/openssl.html)
- [sslshopper.com/article-most-common-openssl-commands](https://www.sslshopper.com/article-most-common-openssl-commands.html)
- [How to determine certificate type from file - Stack Overflow](http://stackoverflow.com/questions/1722181/how-to-determine-certificate-type-from-file)
- [openssl -connect returns wrong certificate - Stack Overflow](http://stackoverflow.com/a/24615393)
- [Check SSL Certificate Expiration Date and More - ShellHacks](http://www.shellhacks.com/en/HowTo-Check-SSL-Certificate-Expiration-Date-from-the-Linux-Shell)
