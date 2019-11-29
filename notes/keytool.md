---
tags: [java]
title: keytool
created: '2019-10-23T08:27:46.438Z'
modified: '2019-11-29T11:47:49.787Z'
---

# keytool

> Key and Certificate Management Tool
> Manages a keystore (database) of cryptographic keys, X.509 certificate chains, and trusted certificates.

## usage
```sh
keytool -list -v -keystore keystore.jks
```

## generating a keypair and certificate signing request for a certificate
```sh
keytool -genkey -alias mydomain -keyalg RSA -keystore keystore.jks -keysize 2048          # generate keystore and keypair

keytool -certreq -alias mydomain -keystore keystore.jks -file mydomain.csr                # generate CSR for an existing keystore

keytool -import -trustcacerts -alias root -file Thawte.crt -keystore keystore.jks         # import root/intermediate cert to existing keystore

keytool -import -trustcacerts -alias mydomain -file mydomain.crt -keystore keystore.jks   # import signed primary cert to an existing keystore

# generate a keystore and a self-signed certificate
keytool -genkey -keyalg RSA -alias selfsigned -keystore keystore.jks -storepass password -validity 360 -keysize 2048        
```

## validate the generation process for certificates and CSRs.
```sh
keytool -printcert -v -file mydomain.crt                  # for checking a standalone certificate

keytool -list -v -keystore keystore.jks                   # for checking which certificates are in a Java keystore

keytool -list -v -keystore keystore.jks -alias mydomain   # for checking a particular keystore entry using an alias

keytool -delete -alias mydomain -keystore keystore.jks    # for deleting a certificate from a Java Keytool keystore

keytool -storepasswd -new new_storepass -keystore keystore.jks              # for changing a Java keystore password

keytool -export -alias mydomain -file mydomain.crt -keystore keystore.jks   # for exporting a certificate from a keystore

keytool -list -v -keystore $JAVA_HOME/jre/lib/security/cacerts              # to view a list of trusted CA certs

# for importing new CAs into your trusted certs
keytool -import -trustcacerts -file /path/to/ca/ca.pem -alias CA_ALIAS -keystore $JAVA_HOME/jre/lib/security/cacerts    
```

## convert pem to jks
```sh
# keystore
openssl pkcs12 \
  -inkey ${common_name}.key.pem \
  -in ${common_name}.bundle.pem \
  -export \
  -out ${common_name}.key.p12 \
  -passout pass:${store_password}

# this seems not really needed as java supports pkcs12 natively nowadays, so we could use ${common_name}.key.p12 as ${common_name}.keystore.jks directly
keytool \
  -importkeystore \
  -srcstoretype ${keystore_type} \
  -srckeystore ${common_name}.key.p12 \
  -keyalg RSA \
  -srcstorepass ${store_password}  \
  -destkeystore ${common_name}.keystore.jks \
  -deststoretype ${keystore_type} \
  -deststorepass ${store_password}

# truststore
keytool \
  -importcert \
  -alias IntermediateCA \
  -file ${common_name}.na-root.pem \
  -keyalg RSA \
  -noprompt \
  -trustcacerts \
  -storepass ${store_password} \
  -keystore ${common_name}.truststore.jks \
  -storetype ${keystore_type}


--------------------------------------------------------------------------------

keytool \
  -importkeystore \
  -srckeystore keystore.jks \
  -srcstorepass changeme \
  -destkeystore identity.p12 \
  -deststoretype PKCS12 \
  -deststorepass password \
  -destkeypass password

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
