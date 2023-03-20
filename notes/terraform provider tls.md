---
tags: [cryptography]
title: terraform provider tls
created: '2020-01-23T07:08:31.402Z'
modified: '2023-03-20T08:58:15.803Z'
---

# terraform provider tls

> allow private keys, certificates and certficate requests to be created as part of a terraform deployment

## usage

```hcl
resource "tls_private_key" "vault" {
  algorithm = "ECDSA"
}

resource "tls_self_signed_cert" "vault" {
  key_algorithm         = tls_private_key.vault.algorithm
  private_key_pem       = tls_private_key.vault.private_key_pem
  is_ca_certificate     = false
  validity_period_hours = 12
  early_renewal_hours   = 3

  # Reasonable set of uses for a server SSL certificate.
  # other X509v3 Key Usage: Certificate Sign, CRL Sign, Digital Signature, Non Repudiation, Key Encipherment, Data Encipherment
  allowed_uses = [
    "key_encipherment",
    "digital_signature",
    "server_auth",
  ]

  subject {
    common_name  = "common.name"
    organization = "organization"
  }
  dns_names = ["dns.name.1", "dns.name.2"]
}

resource "local_file" "cert_pem" {
  filename = "./files/${terraform.workspace}/certs/cert.pem"
  content  = tls_self_signed_cert.vault.cert_pem
}

resource "local_file" "key_pem" {
  filename = "./files/${terraform.workspace}/certs/key.pem"
  content  = tls_private_key.vault.private_key_pem
}

resource "null_resource" "provision_certs" {
  ..
  provisioner "file" {
    source      = local_file.cert_pem.filename
    destination = "/etc/vault/certs/cert.pem"
  }
}
```

## see also

- [[terraform]]
- [terraform.io/docs/providers/tls](https://www.terraform.io/docs/providers/tls/index.html)
