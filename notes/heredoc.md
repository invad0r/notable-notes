---
tags: [linux]
title: heredoc
created: '2019-07-30T06:19:49.079Z'
modified: '2023-03-22T09:55:35.568Z'
---

# heredoc

> here-document is a special-purpose code block. It uses a form of I/O redirection to feed a command list to an interactive program or a command

## usage

```sh
# ignore the leading tab characters
# hyphen just after the << is enough to tell bash to ignore the leading tab characters
<<-     # dash ignores only tab indentation
'EOF'   # single-quotes avoid shell-substitution

cat <<-EOF
	echo $HOME
	echo $$
	cat <<EOT
	echo $HOME
	=====
	EOT
	cat <<'EOB'
	echo $HOME
	EOB
EOF


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

```sh
cat <<EOF > .pre-commit-config.yaml
- repo: git://github.com/antonbabenko/pre-commit-terraform
  rev: v1.7.3
  hooks:
    - id: terraform_fmt
EOF
```

## sudo redirect cat

```sh
sudo ash -c "cat >> /var/config.file" <<EOF
  some config
EOF
```

# sudo redirect tee

```sh
sudo tee /etc/sysconfig/docker-volume-netshare <<-'EOF'
 some config
EOF
```

## docker build

```sh
docker build -t htop - << EOF
FROM alpine
RUN apk --no-cache add htop
EOF
```

## curl data

```sh
curl http://host -d @- <<EOF
{
  "from" : 0,
  "size" : 40
}
EOF
```

## ssh commands

```sh
ssh -T docker@HOST <<EOF
uptime
sudo update -y
EOF
```

## anon heredoc

```sh
: <<TESTVARIABLES
${HOSTNAME?}${USER?}${MAIL?}  # Print error message if one of the variables not set.
TESTVARIABLES
exit $?
```

## using in loop

```sh
while read line; do echo "$line"; done <<EOF
foo
bar
EOF

# export PS2='> '     # used in multiline commands# 
cat <<EOF |
> test
> test1
> EOF
>
> while read line; do
> echo $line;
> done
```

## see also

- [[bash redirects]]
- [[cat]]
- [[yml]]
- [HereDocument - Greg's Wiki](https://mywiki.wooledge.org/HereDocument)
- [Here Documents](http://www.tldp.org/LDP/abs/html/here-docs.html)
- [Nice here document feature I have found recently - ycombinator.com](https://news.ycombinator.com/item?id=7596375)
