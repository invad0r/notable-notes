---
title: vault
created: '2019-09-26T05:56:37.432Z'
modified: '2020-02-04T08:49:16.933Z'
---

# vault

> tool for securely accessing secrets

## usage
```sh
vault -autocomplete-install

$VAULT_TOKEN
$VAULT_ADDR

vault login -address=https://ADDRESS:8200 TOKEN

vault auth -method=ldap username=user

vault status -address=http://ADDRESS:8200

vault secrets list -detailed


vault list secret

vault list int-ca/roles

vault read int-ca/roles/kafka-server


# create a role
vault write int-ca/roles/vault \
  max_ttl="8760h" \
  allowed_domains="vault*" \
  allow_subdomains=true \
  allow_glob_domains=true


# redirecting from tee to multiple files
vault write -format=json pki/root/generate/internal common_name="pki-ca-root" ttl=87600h \
   | tee \
    >(jq -r .data.certificate > ca.pem) \
    >(jq -r .data.issuing_ca > issuing_ca.pem) \
    >(jq -r .data.private_key > ca-key.pem)
```

## see also
- [[consul]]
- [[terraform]]
- [[tee]]
- [[jq]]
- [[bash process substitution]]
