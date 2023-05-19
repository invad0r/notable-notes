---
tags: [Notebooks]
title: servicemesh
created: '2020-05-11T06:38:47.231Z'
modified: '2023-05-16T15:34:01.898Z'
---

# servicemesh

- fundamentaly an overlay network
- differs from `VXLAN` in that it operates at `layer 3` rather than `layer 2`
- `TLS` encrypted
- instead of shared `VTEP`'s there is an Envoy proxy instance per service endpoint

### implications

- all traffic in the mesh is encrypted by default
- traditional security technologies (layer 2 IDS/IPS) will not function as desired due to encryption
- servicemesh-endpoints can be placed anywhere that has `layer 3` connectivity with the other mesh endpoints (on premise, cloud, etc)

## see also

- [[istioctl]]
- [[kubectl]]
- [[microservice]]
- [[docker network]]
