---
tags: [cryptography]
title: jwt
created: '2020-01-27T08:04:24.079Z'
modified: '2022-02-01T14:58:49.263Z'
---

# jwt

> `json web tokens` - standard `RFC 7519` method for representing claims securely between two parties

`jwt`'s consist of three parts separated by dots: `HEADER.PAYLOAD.SIGNATURE`

## usage

```sh
jq -R 'split(".") | .[1] | @base64d | fromjson' <<< "$TOKEN"    # decode to json
```

## see also

- [[jq]]
- [jwt.io/introduction](https://jwt.io/introduction/)
- [github.com/emcrisostomo/jwt-cli](https://github.com/emcrisostomo/jwt-cli)
- [willhaley.com/blog/generate-jwt-with-bash](https://willhaley.com/blog/generate-jwt-with-bash/)
- [jvt.me/posts/2019/06/13/pretty-printing-jwt-openssl](https://www.jvt.me/posts/2019/06/13/pretty-printing-jwt-openssl/)
- [gist.github.com/rolandyoung/176dd310a6948e094be6](https://gist.github.com/rolandyoung/176dd310a6948e094be6)
- [github.com/Moodstocks/moodstocks-api-clients/blob/master/bash/base64url.sh](https://github.com/Moodstocks/moodstocks-api-clients/blob/master/bash/base64url.sh)
