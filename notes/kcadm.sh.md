---
title: kcadm.sh
created: '2020-02-03T09:34:38.160Z'
modified: '2021-06-04T12:25:49.726Z'
---

# kcadm.sh

> admin cli works by making http requests to admin REST endpoints - access to them is protected and requires auth

## install

```sh
curl -O https://downloads.jboss.org/keycloak/8.0.1/keycloak-8.0.1.tar.gz
tar xzf keycloak-8.0.1.tar.gz && mv keycloak-8.0.1 ~/bin
export PATH="$PATH:$HOME/bin/keycloak-8.0.1/bin"
```

## flags

```sh
-r, --target-realm REALM        # Target realm to issue requests against if not the one authenticated against
-q, --query NAME=VALUE          # Add to request URI a NAME query parameter with value VALUE
-h, --header NAME=VALUE         # Set request header NAME to VALUE
-o, --offset OFFSET             # Set paging offset - adds a query parameter 'first' which some endpoints recognize
-l, --limit LIMIT               # Set limit to number of items in result - adds a query parameter 'max' which some endpoints recognize
-H, --print-headers             # Print response headers
-F, --fields FILTER             # A filter pattern to specify which fields of a JSON response to output
-c, --compressed                # Don't pretty print the output
--format FORMAT                 # Set output format to comma-separated-values by using 'csv'. Default format is 'json'
--noquotes                      # Don't quote strings when output format is 'csv'
-a, --admin-root URL            # URL of Admin REST endpoint root if not default - e.g. http://localhost:8080/auth/admin
```

## usage

```sh
kcadm.sh config credentials --server http://keycloak/auth --realm master --user admin   # .keycloak/kcadm.config

kcadm.sh get ENDPOINT [ARGUMENTS]

kcadm.sh get serverinfo

kcadm.sh get realms


kcadm.sh get realms/REALM

kcadm.sh get clients -r REALM --fields id,clientId

kcadm.sh get clients/CLIENT_ID -r REALM

kcadm.sh get clients/CLIENT_ID/roles -r REALM

kcadm.sh get clients/CLIENT_ID/client-secret -r REALM

kcadm.sh get clients/CLIENT_ID/installation/providers/keycloak-oidc-keycloak-json -r REALM    # also contains credentials/secret !


./kcadm.sh create realms -s realm=foo -s enabled=true     # Create Realm foo

# Create a REST API client
./kcadm.sh create clients \
  -r foo  -s clientId=foo-api  -s enabled=true  \
  -s clientAuthenticatorType=client-secret \
  -s 'redirectUris=["http://localhost:8001/*"]' \
  -s serviceAccountsEnabled=true                          # Creates new client with id '64daa1f8-3859-4b1a-a5ee-c1ae54d1ab69'

# Create User role
./kcadm.sh create clients/CLIENT_ID/roles -r corbee -s name=user -s 'description=User role'
```

## see also

- [[keycloak api]]
- [[java]]
- [keycloak.org/docs/8.0/server_admin/#the-admin-cli](https://www.keycloak.org/docs/8.0/server_admin/#the-admin-cli)
