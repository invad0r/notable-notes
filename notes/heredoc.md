---
tags: [bash, heredoc, linux]
title: heredoc
created: '2019-07-30T06:19:49.079Z'
modified: '2019-08-01T07:13:52.955Z'
---

# heredoc

> "here document is a special-purpose code block. It uses a form of I/O redirection to feed a command list to an interactive program or a command

## promt
```sh
export PS2='> ' # used in multiline commands
```

## ignore the leading tab characters
hyphen just after the << is enough to tell bash to ignore the leading tab characters.
```sh
<<-   # dash ignores only tab indentation
'EOF' # single-quotes avoid shell-substitution
```
```sh
echo 1
# must use tabs for indentation !!!
  grep $1 <<-'EOF'
    lots of data
    can go here
    it's indented with tabs
    to match the script's indenting
    but the leading tabs are
    discarded when read
    EOF
ls
```
[HereDocument - Greg's Wiki](https://mywiki.wooledge.org/HereDocument)

## cat

```sh
cat <<EOF > .pre-commit-config.yaml
- repo: git://github.com/antonbabenko/pre-commit-terraform
  rev: v1.7.3
  hooks:
    - id: terraform_fmt
EOF
```
[Here Documents](http://www.tldp.org/LDP/abs/html/here-docs.html)

### sudo redirect cat
```sh
sudo ash -c "cat >> /var/config.file" <<EOF
  some config
EOF
```

### sudo redirect tee
```sh

sudo tee /etc/sysconfig/docker-volume-netshare <<-'EOF'
 some config
EOF
```

### docker build
```sh
docker build -t htop - << EOF
FROM alpine
RUN apk --no-cache add htop
EOF
```

    
### curl data
```sh
curl http://localhost -d @- <<REQUEST_BODY
{
  "from" : 0,
  "size" : 40
}
REQUEST_BODY
```
[Nice here document feature I have found recently is heredoc with pipe, e.g. c... | Hacker News](https://news.ycombinator.com/item?id=7596375)

### ssh commands
```sh
ssh -T docker@HOST <<EOSSH
uptime
sudo update -y
EOSSH
```


### anon heredoc

```sh
#!/bin/bash

: <<TESTVARIABLES
${HOSTNAME?}${USER?}${MAIL?}  # Print error message if one of the variables not set.
TESTVARIABLES

exit $?
```

### using in loop

```sh
while read line; do
  echo $line
done <<EOF
foo
bar
EOF
```

```sh
cat <<EOF |
> test
> test1
> EOF
>
> while read line; do
> echo $line;
> done
```

https://docs.gitlab.com/ee/development/changelog.html
[Changelog entries \| GitLab](https://docs.gitlab.com/ee/development/changelog.html)
