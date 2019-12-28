---
title: a2ensite a2dissite
created: '2019-12-28T15:45:07.030Z'
modified: '2019-12-28T15:49:09.947Z'
---

# a2ensite a2dissite
> enable or disable an apache2 site / virtual host 
## usage
```sh
a2ensite vhosts_nam.com.conf   # enable site

a2dissite 000-default

# flags:
# -q, --quiet         don't show informative messages.
# -m, --maintmode     enables the maintainer mode
# -p, --purge         purge all traces of the module in the internal state data base
```

## see also
- [[apache2]]
- [[a2enmod]]
- https://manpages.debian.org/jessie/apache2/a2ensite.8.en.html
