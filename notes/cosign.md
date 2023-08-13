---
tags: [container, crypto, linux, macos]
title: cosign
created: '2023-07-04T11:18:58.179Z'
modified: '2023-07-19T11:19:31.595Z'
---

# cosign

> securely sign artifacts (release files, container images, binaries, bill of material manifests..) 
> signing materials are then stored in a tamper-resistant public log

## install

```sh
brew install cosign
```

## env

```sh
COSIGN_PASSWORD
```

## usage

```sh
cosign sign-blob FILE --output-signature FILE --output-certificate FILE # sign a blob with google sign-in (experimental)

cosign sign-blob --key cosign.key FILE                                  # sign a blob with a local key pair file

cosign sign-blob --key awskms://[ENDPOINT]/[ID/ALIAS/ARN] FILE          # sign a blob with a key pair stored in aws kms

cosign sign-blob --key gcpkms://projects/[PROJECT]/locations/global/keyRings/[KEYRING]/cryptoKeys/[KEY] FILE # sign a blob with a key pair stored in Google Cloud KMS

cosign sign-blob --key hashivault://[KEY] FILE # sign a blob with a key pair stored in Hashicorp Vault
```

## see also

- [[docker]]
- [[crane]]
- [[gpg]]
- [[vault]]
- [[openssl]]
- [[uuidgen]]
