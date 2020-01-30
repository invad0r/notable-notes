---
title: jwt
created: '2020-01-27T08:04:24.079Z'
modified: '2020-01-27T08:42:43.438Z'
---

# jwt

> JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties

## usage
```sh
# jwt's consist of three parts separated by dots `.`, which are:
#    Header
#    Payload
#    Signature

xxxxx.yyyyy.zzzzz

jq -R 'split(".") | .[1] | @base64d | fromjson' <<< "$TOKEN"    # decode to json
```
## see also
- [[jq]]
- https://jwt.io/introduction/
- https://github.com/emcrisostomo/jwt-cli
- https://willhaley.com/blog/generate-jwt-with-bash/
- https://www.jvt.me/posts/2019/06/13/pretty-printing-jwt-openssl/
- https://gist.github.com/rolandyoung/176dd310a6948e094be6
- https://github.com/Moodstocks/moodstocks-api-clients/blob/master/bash/base64url.sh
