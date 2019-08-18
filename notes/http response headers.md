---
tags: [network]
title: http response headers
created: '2019-08-14T06:11:13.558Z'
modified: '2019-08-14T06:23:42.171Z'
---

# http response headers

- `age`
- `date` 
  - when response was sent
- `last-modified`
- `etag` 
  - hash of response body
- `cache-control`
- `vary` 
- `via`
  - added by proxy-server example `via: nginx`
- `expires`
- `connection` 
- `set-cookie` 
- `access-control-*` 
  - called cors-headers, these allow cross-origin request
- `conten-type`
  - goes with accept: request header 
  - example `image/png`
- `content-length` 
  - length of body in bytes
  - example: "12954"
- `content-language` 
  - goes with accept-language request header
  - example: "en-US"
- `content-encoding` 
  -  goes with accept-econgin request header
  - example: "gzip"
- `location` 
  - URL to redirect to for a `3xx` response
- `accept-ranges`

### x-headers
example custom headers used by browsers:
`x-frame-options: DENY`
`x-content-type-options: nosniff`
`x-ua-compatible: IE=edge`
`x-xss-protextion: 1; mode=block`
