---
tags: [iac]
title: vault
created: '2019-09-26T05:56:37.432Z'
modified: '2023-07-04T11:25:41.630Z'
---

# vault

> tool for securely accessing secrets

## usage

```sh
vault -autocomplete-install     # setup

# export to use agent against server or use login
VAULT_TOKEN
VAULT_ADDR

vault login -address=https://ADDRESS:8200 TOKEN


vault auth -method=ldap username=user


vault status -address=http://ADDRESS:8200


vault secrets list -detailed


vault token lookup TOKEN

vault token capabilities int-ca/issue/kafka   # need token already set !


vault list secret

vault list int-ca/roles

vault read int-ca/roles/kafka-server


vault write -output-curl-string SECRET    # generate curl

# create a role
vault write int-ca/roles/vault \
  max_ttl="8760h" allowed_domains="vault*" allow_subdomains=true allow_glob_domains=true

# redirecting from tee to multiple files
vault write -format=json pki/root/generate/internal common_name="pki-ca-root" ttl=87600h \
   | tee  >(jq -r .data.certificate > cert.pem)  >(jq -r .data.issuing_ca > intermediate.pem) >(jq -r .data.private_key > key.pem)

vault write transit/path/encrypt/foo plaintext=$(base64 <<< "my secret data")            # encrypt data

vault write transit/path/decrypt/foo ciphertext=vault:v1:3kd1XR2w1lk..8KIWy2VVBA==       # decrypt data
```

## see also

- [[consul]]
- [[terraform]]
- [[tee]]
- [[jq]]
- [[bash process substitution]]
- [[cosign]]

