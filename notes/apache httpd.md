---
tags: [linux]
title: apache httpd
created: '2019-07-30T06:19:48.985Z'
modified: '2019-11-28T11:55:22.213Z'
---

# apache httpd

> `A Patchy Server`

```sh
# prerequesite
source /etc/apache2/envvars \
apache2 -S                      # Show settings as parsed from the config file
```

```sh
a2enmode ssl                    # enable-modules

# /server-status
a2enmod info.load
a2enmod info.conf  # vim /etc/apach2/mods-available/info.conf => comment Require to access outside localhost
service apache2 restart

a2ensite vhosts_nam.com.conf   # enable site
```

## see also
- [[apachectl]]
- [Generate Mozilla Security Recommended Web Server Configuration Files](https://mozilla.github.io/server-side-tls/ssl-config-generator/)
