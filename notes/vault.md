---
title: vault
created: '2019-09-26T05:56:37.432Z'
modified: '2019-11-29T11:49:21.034Z'
---

# vault

## usage
```sh
# $VAULT_TOKEN $VAULT_ADDR should be set when interacting with cli

vault status

vault list secret

vault secrets list -detailed
```

## roles
```sh
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
- [[tee]]
