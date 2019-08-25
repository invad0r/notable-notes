---
tags: [linux]
title: apache httpd
created: '2019-07-30T06:19:48.985Z'
modified: '2019-08-25T19:58:50.919Z'
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

## apachectl

### test config
```sh
apachectl configtest          

/usr/local/apache/bin/apachectl configtest
```
### list modules
```sh
apache2ctl -M                     # list loaded modules

apachectl -t -D DUMP_MODULES      # list loaded modules

ls /etc/apache2/mods-enabled/		  # list enabled modules
ls /etc/apache2/mods-available/		# list available modules
```

## see also
- [Generate Mozilla Security Recommended Web Server Configuration Files](https://mozilla.github.io/server-side-tls/ssl-config-generator/)
