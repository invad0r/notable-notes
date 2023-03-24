---
tags: [python]
title: http
created: '2023-03-23T08:51:29.253Z'
modified: '2023-03-23T08:55:59.995Z'
---

# http

>  `HTTPie` - client, aims to be easier to use than [[curl]]

## install

```sh
brew    install httpie
apt-get install httpie 
```

## usage

```sh
http --download URL                   # download URL

http URL name='bob'                   # Send JSON object

http METHOD URL                       # Specify a METHOD: "HEAD", "GET",..

http URL X-MyHeader:123               # Include an extra header

http --auth username:password URL     # Pass a username and password for server authentication

cat data.txt | http PUT URL            # Specify raw request body via stdin

http --form example.org name='bob' profile_picture@'bob.png'      # Send form-encoded data
```

## see also

- [[hyper text transfer protocol]]
- [httpie.org](https://httpie.org)
