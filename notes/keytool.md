---
tags: [java]
title: keytool
created: '2019-10-23T08:27:46.438Z'
modified: '2020-03-02T15:34:41.582Z'
---

# keytool

> manages keystore (database) of cryptographic keys, X.509 certificate chains, and trusted certificates

## installs
`part of the standard java distribution`

## usage
```sh
keytool -list -v -keystore keystore.jks       # list contents of store


# generating a keypair and certificate signing request for a certificate
keytool -genkey -alias mydomain -keyalg RSA -keystore keystore.jks -keysize 2048          # generate keystore and keypair

keytool -certreq -alias mydomain -keystore keystore.jks -file mydomain.csr                # generate CSR for an existing keystore

keytool -import -trustcacerts -alias root -file Thawte.crt -keystore keystore.jks         # import root/intermediate cert to existing keystore

keytool -import -trustcacerts -alias mydomain -file mydomain.crt -keystore keystore.jks   # import signed primary cert to an existing keystore

# generate a keystore and a self-signed certificate
keytool -genkey -keyalg RSA -alias selfsigned -keystore keystore.jks -storepass password -validity 360 -keysize 2048        


# validate the generation process for certificates and CSRs.
keytool -printcert -v -file mydomain.crt                  # for checking a standalone certificate

keytool -list -v -keystore keystore.jks                   # for checking which certificates are in a Java keystore

keytool -list -v -keystore keystore.jks -alias mydomain   # for checking a particular keystore entry using an alias

keytool -delete -alias mydomain -keystore keystore.jks    # for deleting a certificate from a Java Keytool keystore

keytool -storepasswd -new new_storepass -keystore keystore.jks              # for changing a Java keystore password

keytool -export -alias mydomain -file mydomain.crt -keystore keystore.jks   # for exporting a certificate from a keystore

keytool -list -v -keystore $JAVA_HOME/jre/lib/security/cacerts              # to view a list of trusted CA certs

# for importing new CAs into your trusted certs
keytool -import -trustcacerts -file /path/to/ca/ca.pem -alias CA_ALIAS -keystore $JAVA_HOME/jre/lib/security/cacerts    


# convert pem to jks
# keystore
openssl pkcs12 -inkey key.pem -in bundle.pem -export -out key.p12 -passout pass:PASSWORD

# this seems not really needed as java supports pkcs12 natively nowadays, so we could use key.p12 as keystore.jks directly
keytool -importkeystore -srcstoretype KEYSTORETYPE -srckeystore key.p12 -keyalg RSA -srcstorepass STOREPASS  \
  -destkeystore keystore.jks -deststoretype KEYSTORETYPE -deststorepass STOREPASS

# truststore
keytool -importcert -alias IntermediateCA -file na-root.pem -keyalg RSA -noprompt -trustcacerts \
  -storepass STOREPASS -keystore truststore.jks -storetype KEYSTORETYPE

keytool -importkeystore -srckeystore keystore.jks -srcstorepass changeme -destkeystore identity.p12 \
  -deststoretype PKCS12 -deststorepass password -destkeypass password

#  -srckeypass changeme \
#  -srcalias IntermediateCA \
#  -destalias IntermediateCA \


openssl pkcs12 -in identity.p12 -nodes -nocerts -out private_key.pem
openssl pkcs12 -in identity.p12  -clcerts -nokeys -out publicCert.pem

keytool -export -alias IntermediateCA -file ca-chain.p12 -keystore truststore.jks
openssl pkcs12 -in ca-chain.p12  -clcerts -nokeys -out ca-chain.pem


openssl s_client -connect host:9094 -CAfile rootCA.PEM.crt -cert cert.pem -key key.pem
```

## see also
- [[openssl]]
- https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html
- https://dzone.com/articles/understand-java-keytool-keystore-commands
