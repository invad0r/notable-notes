---
tags: [linux]
title: apache2
created: '2019-07-30T06:19:48.985Z'
modified: '2019-12-28T15:44:40.909Z'
---

# apache2
> `A Patchy Server`

## usage
```sh
# prerequesite
source /etc/apache2/envvars \
apache2 -S                      # Show settings as parsed from the config file

service apache2 restart
```

## see also
- [[apachectl]]
- [[a2enmod]]
- [Generate Mozilla Security Recommended Web Server Configuration Files](https://mozilla.github.io/server-side-tls/ssl-config-generator/)
