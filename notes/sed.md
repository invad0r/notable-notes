---
tags: [linux]
title: sed
created: '2019-07-30T06:19:49.228Z'
modified: '2019-08-23T11:01:53.073Z'
---

# sed

`Stream EDitor`

### substitution
```sh
sed 's/[^a-zA-Z0-9]//g'                       # remove non-alphanumeric characters

sed -i.tmp 's/^/\t/' *.txt                    # keep copy with extension .tmp   .. osx must provide an extension !
                                              # -i, --in-place

sed -i ''  's/^/\t/'  *.txt                   # without creating a backup, you can use

sed -i '4d' vector-out-of-bounds.cpp          # delete line 4

sed -i '5s/#/\/\//' vector-out-of-bounds.cpp  # in line 5 substitute '#' with '//'

sed -i '/2018-01-30/!d' file.log              # delete all lines except ones matching pattern


sed -i 's/\(^ExecStart=\).*/ExecStart=\/usr\/bin\/dockerd -H tcp:\/\/0.0.0.0:2375/' /lib/systemd/system/docker.service

sed -i 's/\(^#DOCKER_OPTS=\).*/DOCKER_OPTS="-H tcp:\/\/0.0.0.0:2375"/' /etc/default/docker
```


### using different delimiter
```sh
sed -i "s%\$$1%${val}%g" $CONF_PATH   #  %-delimiter to avoid escaping slashes in URLs

sed -n -e 's,.*/bin/sh -c #(nop) \(MAINTAINER .*[^ ]\) *0 B,\1,p'    # ,-delimiter
```

## greedy
```sh
% echo "<b>foo</b>bar" | sed 's/<.*>//g'
bar

Non greedy matching:

% echo "<b>foo</b>bar" | sed 's/<[^>]*>//g'
foobar
```

## see also
- [Sed - An Introduction and Tutorial](http://www.grymoire.com/Unix/Sed.html)
- [0x2a.at - sed - non greedy matching](https://0x2a.at/blog/2008/07/sed--non-greedy-matching/)
