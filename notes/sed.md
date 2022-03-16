---
tags: [linux]
title: sed
created: '2019-07-30T06:19:49.228Z'
modified: '2022-01-31T14:00:17.343Z'
---

# sed

> `Stream EDitor`

## usage

```sh
sed "${NUM}q;d" FILE                          # print line from file

sed -n "2p"                                   # print second line only

sed -n '2{p;q}' FILE                          # in case there will be no more line 2 after line 2, spare pointless processing by `q`uiting after `p`rinting

sed -i '/2018-01-30/!d' FILE                  # delete all lines except ones matching pattern

sed -i '4d' FILE                              # delete line 4
sed    '/STRING/d' d                          # delete line containing STRING

sed '/INCLUDE/ r foo.h'                       #  insert foo.h after 'INCLUDE'


# substitution

sed -r "s/[[:cntrl:]]\[[0-9]{1,3}m//g"        # remove colors from output

sed 's/[^a-zA-Z0-9]//g'                       # remove non-alphanumeric characters

sed -i.tmp 's/^/\t/' *.txt                    # keep copy with extension .tmp   .. osx must provide an extension !
                                              # -i, --in-place
sed -i ''  's/^/\t/'  *.txt                   # without creating a backup, you can use

sed -i '5s/#/\/\//' vector-out-of-bounds.cpp  # in line 5 substitute '#' with '//'

sed -i 's/\(^ExecStart=\).*/ExecStart=\/usr\/bin\/dockerd -H tcp:\/\/0.0.0.0:2375/' /lib/systemd/system/docker.service

sed -i 's/\(^#DOCKER_OPTS=\).*/DOCKER_OPTS="-H tcp:\/\/0.0.0.0:2375"/' /etc/default/docker


sed -i "s%\$$1%${val}%g" $CONF_PATH   # % as delimiter to avoid escaping slashes in URLs

sed -n -e 's,.*/bin/sh -c #(nop) \(MAINTAINER .*[^ ]\) *0 B,\1,p'    # , as delimiter


echo "<b>foo</b>bar" | sed 's/<.*>//g'      #     greedy matching: "bar"
echo "<b>foo</b>bar" | sed 's/<[^>]*>//g'   # non greedy matching: "foobar"
```

## see also

- [[tr]]
- [[cut]]
- [[awk]]
- [grymoire.com/Unix/Sed](http://www.grymoire.com/Unix/Sed.html)
- [0x2a.at/blog/2008/07/sed--non-greedy-matching](https://0x2a.at/blog/2008/07/sed--non-greedy-matching/)
- [github.com/adrianscheff/useful-sed](https://github.com/adrianscheff/useful-sed)
