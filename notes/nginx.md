---
tags: [lua]
title: nginx
created: '2021-08-31T08:55:05.976Z'
modified: '2023-05-05T08:15:51.100Z'
---

# nginx

>

## option

```sh
-?,-h             # show help
-v                # show version and exit
-V                # show version and configure options then exit
-t                # test configuration and exit
-T                # test configuration, dump it and exit
-q                # suppress non-error messages during configuration testing
-s signal         # send signal to a master process: stop, quit, reopen, reload
-p prefix         # set prefix path (default: /etc/nginx/)
-e filename       # set error log file (default: /var/log/nginx/error.log)
-c filename       # set configuration file (default: /etc/nginx/nginx.conf)
-g directives     # set global directives out of configuration file
```

## module

```sh
ngx_http_core_module

Syntax: 	try_files file ... uri;
          try_files file ... =code;
Context: 	server, location


Syntax: 	error_page code ... [=[response]] uri;
Context: 	http, server, location, if in location


Syntax: 	error_log file [level];
          error_log logs/error.log error;

          level: debug, info, notice, warn, error, crit, alert, or emerg
Context: 	main, http, mail, stream, server, location
```

## see also

- [nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls](https://www.nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls/)
