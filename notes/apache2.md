---
tags: [linux]
title: apache2
created: '2019-07-30T06:19:48.985Z'
modified: '2020-09-08T07:31:14.843Z'
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


apachectl configtest                # test config

/usr/local/apache/bin/apachectl configtest


apache2ctl -M                     # list loaded modules

apachectl -t -D DUMP_MODULES      # list loaded modules

ls /etc/apache2/mods-enabled/		  # list enabled modules
ls /etc/apache2/mods-available/		# list available modules




# enable apche2 modules
a2enmode ssl                    # enable-modules

a2enmod info.load               # /server-status

a2enmod info.conf  
# vim /etc/apach2/mods-available/info.conf => comment Require to access outside localhost



# enable or disable an apache2 site / virtual host 
a2ensite vhosts_nam.com.conf   # enable site

a2dissite 000-default

# flags:
# -q, --quiet         don't show informative messages.
# -m, --maintmode     enables the maintainer mode
# -p, --purge         purge all traces of the module in the internal state data base
```

## see also
- [Generate Mozilla Security Recommended Web Server Configuration Files](https://mozilla.github.io/server-side-tls/ssl-config-generator/)
- [manpages.debian.org/jessie/apache2/a2ensite.8.en.html](https://manpages.debian.org/jessie/apache2/a2ensite.8.en.html)
