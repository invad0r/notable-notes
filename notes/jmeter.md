---
title: jmeter
created: '2023-03-17T06:55:48.163Z'
modified: '2023-03-17T07:04:15.761Z'
---

# jmeter

## install

```sh
skd install jmeter
```

## flags

```sh
-?, --?                           # print command line options and exit
-h, --help                        # print usage information and exit
-v, --version                     # print the version information and exit
-p, --propfile ARG                # the jmeter property file to use
-q, --addprop ARG                 # additional JMeter property file(s)
-t, --testfile ARG                # the jmeter test(.jmx) file to run. "-t LAST" will load last used file
-l, --logfile ARG                 # the file to log samples to
-i, --jmeterlogconf ARG           # jmeter logging configuration file (log4j2.xml)
-j, --jmeterlogfile ARG           # jmeter run log file (jmeter.log)
-n, --nongui                      # run JMeter in nongui mode
-s, --server                      # run the JMeter server
-E, --proxyScheme ARG             # set a proxy scheme to use for the proxy server
-H, --proxyHost ARG               # set a proxy server for JMeter to use
-P, --proxyPort ARG               # set proxy server port for JMeter to use
-N, --nonProxyHosts ARG           # set nonproxy host list (e.g. *.apache.org|localhost)
-u, --username ARG                # set username for proxy server that JMeter is to use
-a, --password ARG                # set password for proxy server that JMeter is to use
-J, --jmeterproperty ARG=VAL      # define additional JMeter properties
-G, --globalproperty ARG=VAL      # define Global properties (sent to servers) e.g. -Gport=123 or -Gglobal.properties
-D, --systemproperty ARG=VAL      # define additional system properties
-S, --systemPropertyFile ARG      # additional system property file(s)
-f, --forceDeleteResultFile       # force delete existing results files and web report folder if present before starting the test
-L, --loglevel ARG=VAL            # [category=]level e.g. jorphan=INFO, jmeter.util=DEBUG or com.example.foo=WARN
-r, --runremote                   # Start remote servers (as defined in remote_hosts)
-R, --remotestart ARG             # Start these remote servers (overrides remote_hosts)
-d, --homedir ARG                 # the jmeter home directory to use
-X, --remoteexit                  # Exit the remote servers at end of test (non-GUI)
-g, --reportonly ARG              # generate report dashboard only, from a test results file
-e, --reportatendofloadtests      # generate report dashboard after load test
-o, --reportoutputfolder ARG      # output folder for report dashboard
```

## usage

```sh
jmeter -n -t FILE.jmx -l FILE.log -e -o ./REPORT/OUT_DIR -Jpropertie=${VAL}
```

## see also

- [[sdk]]
- [[java]]
