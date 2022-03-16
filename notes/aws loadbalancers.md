---
title: aws loadbalancers
created: '2022-02-15T13:21:52.943Z'
modified: '2022-02-15T13:36:42.973Z'
---

# aws loadbalancers

```sh
Feature 	                    . Application LB    	    Network LB    	    Gateway LB    	                  Classic LB
                              .
LB type 	                    . L7                      L4     	            L3 Gateway + L4 Load Balancing 	  L4/7
Target type 	                . IP, Instance, Lambda 	  IP, Instance, ALB 	IP, Instance 	 
Terminates                    .
flow/proxy behavior 	        . Yes 	                  Yes 	              No 	                              Yes
Protocol listeners 	          . HTTP, HTTPS, gRPC 	    TCP, UDP, TLS 	    IP 	                              TCP, SSL/TLS, HTTP, HTTPS
Reachable via 	              . VIP 	                  VIP 	              Route table entry       	        -
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   
Layer 7                       .
                              .
Redirects 	                  .   ✔ 	  	  	 
Fixed Response 	              .   ✔ 	  	  	 
Desync Mitigation Mode 	      .   ✔ 	  	  	 
HTTP header based routing 	  .   ✔ 	  	  	 
HTTP2/gRPC 	                  .   ✔ 	  	  	 
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 

Common configurations and characteristics

Slow start 	                 . ✔ 	  	  	 
Outpost support           	 . ✔ 	  	  	 
Local Zone 	                 . ✔ 	  	  	 
IP address - Static, Elastic . ✔ 	  	 
Connection draining (deregistration delay) 	✔ 	✔ 	✔ 	✔
Configurable idle connection timeout 	✔ 	  	  	✔
PrivateLink Support 	  	✔ (TCP, TLS) 	✔ (GWLBE) 	 
Zonal Isolation 	  	✔ 	✔ 	 
Session resumption 	✔ 	✔ 	  	 
Long-lived TCP connection 	  	✔ 	✔ 	 
Load Balancing to multiple ports on the same instance 	✔ 	✔ 	✔ 	 
Load Balancer deletion protection 	✔ 	✔ 	✔ 	 
Preserve Source IP address 	✔ 	✔ 	✔ 	 
WebSockets 	✔ 	✔ 	✔ 	 
Supported network/Platforms 	VPC 	VPC 	VPC 	EC2-Classic, VPC
Cross-zone Load Balancing 	✔ 	✔ 	✔ 	✔
IAM Permissions(Resource, Tag based) 	✔ 	✔ 	✔ 	✔ (Only resource based)

Flow Stickiness 
(All packets of a flow are sent 
 to one target, and return 
 traffic comes from same target) 	Symmetric 	Symmetric 	Symmetric 	Symmetric

Target Failure behavior
	Fail close on targets, unless all targets are unhealthy(fail open) 	Fail close on targets, unless all targets are unhealthy(fail open) 	Existing flows continue to go to existing target appliances, new flows are rerouted to healthy target appliances. 	 
Health Checks 	                    HTTP, HTTPS, gRPC 	  TCP, HTTP, HTTPS 	  TCP, HTTP, HTTPS 	    TCP, SSL/TLS, HTTP, HTTPS

. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 

Security

SSL Offloading 	              ✔ 	✔ 	  	✔
Server Name Indication (SNI) 	✔ 	✔ 	  	 
Back-end Server Encryption 	  ✔ 	✔ 	  	✔
User Authentication 	        ✔ 	  	  	 
Custom Security Policy 	  	  	  	✔
ALPN 	                        ✔ 	✔ 	  	 

. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 

Kubernetes Controller

Direct-to-pod 	            ✔ 	✔ (Fargate pods) 	  	 
Load Balance to 
multiple namespaces 	      ✔ 	  	  	 
Support for fully 
private EKS clusters 	      ✔ 	✔ 	  	 
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 

Logging and monitoring

CloudWatch Metrics 	        ✔ 	        ✔ 	        ✔ 	        ✔
Logging 	                  ✔ 	        ✔ 	        ✔ 	        ✔
```

## see also

- [aws.amazon.com/elasticloadbalancing/features/#compare](https://aws.amazon.com/elasticloadbalancing/features/#compare)
- [[kubectl]] 
- [[eksctl]] 
- [[aws]]
