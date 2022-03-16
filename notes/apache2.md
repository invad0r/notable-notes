---
tags: [linux]
title: apache2
created: '2019-07-30T06:19:48.985Z'
modified: '2022-02-02T08:52:55.070Z'
---

# apache2

> `A Patchy Server` and package

## install

`apt-get install apache2`

## usage

```sh
# prerequesite
source /etc/apache2/envvars \
apache2 -S                      # Show settings as parsed from the config file
apache2 -v

service apache2 restart
```

## apachectl

```sh

apachectl configtest                # test config

/usr/local/apache/bin/apachectl configtest


apache2ctl -M                     # list loaded modules

apachectl -t -D DUMP_MODULES      # list loaded modules

ls /etc/apache2/mods-enabled/		  # list enabled modules
ls /etc/apache2/mods-available/		# list available modules
```

## a2enmode

```sh
a2enmode ssl                    # enable-modules

a2enmod info.load               # /server-status

a2enmod info.conf  
# vim /etc/apach2/mods-available/info.conf => comment Require to access outside localhost
```

## a2ensite

```sh
a2ensite vhosts_nam.com.conf   # enable site / virtual host 
```

```sh
-q, --quiet           # don't show informative messages.
-m, --maintmode       # enables the maintainer mode
-p, --purge           # purge all traces of the module in the internal state data base
```

```sh
a2dissite 000-default
```

## see also

- [Generate Mozilla Security Recommended Web Server Configuration Files](https://mozilla.github.io/server-side-tls/ssl-config-generator/)
- [manpages.debian.org/jessie/apache2/a2ensite.8.en.html](https://manpages.debian.org/jessie/apache2/a2ensite.8.en.html)
