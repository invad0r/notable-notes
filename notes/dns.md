---
tags: [dns]
title: dns
created: '2019-07-30T06:19:49.040Z'
modified: '2023-03-20T08:28:39.786Z'
---

# dns

> domain name system

- port 53 UDP/TCP
- `RFC 882` -> `RFC 1034`
- `RFC 883` -> `RFC 1035`
- "forward lookup"
- DNS-DB: NameServer
- ZoneFile: SOA (=Start of Authority), NAS, A, AAAA, CNAME, MX, PTR, TXT


## namespace

## zone

## record

> administrative concept, defines a part of the DNS namespace

## resource records

```sh
Resource records
Type 	    Type ID 	Defining RFC 	Description 	        Function
A 	        1 	    RFC 1035 	    Address record 	      Returns a 32-bit IPv4 address, most commonly used to map hostnames to an IP address of the host, but it is also used for DNSBLs, storing subnet masks in RFC 1101, etc.
AAAA 	      28 	    RFC 3596 	    IPv6 address record 	Returns a 128-bit IPv6 address, most commonly used to map hostnames to an IP address of the host.
AFSDB 	    18 	    RFC 1183 	    AFS database record 	Location of database servers of an AFS cell. This record is commonly used by AFS clients to contact AFS cells outside their local domain. A subtype of this record is used by the obsolete DCE/DFS file system.
APL 	      42 	    RFC 3123 	    Address Prefix List 	Specify lists of address ranges, e.g. in CIDR format, for various address families. Experimental.
CAA 	      257 	  RFC 6844 	    Certification Authority Authorization 	DNS Certification Authority Authorization, constraining acceptable CAs for a host/domain
CDNSKEY 	  60 	    RFC 7344 	Child copy of DNSKEY record, for transfer to parent
CDS 	      59 	    RFC 7344 	Child DS 	Child copy of DS record, for transfer to parent
CERT 	      37 	    RFC 4398 	Certificate record 	Stores PKIX, SPKI, PGP, etc.
CNAME 	    5 	    RFC 1035 	Canonical name record 	Alias of one name to another: the DNS lookup will continue by retrying the lookup with the new name.
CSYNC 	    62 	    RFC 7477 	Child-to-Parent Synchronization 	Specify a synchronization mechanism between a child and a parent DNS zone. Typical example is declaring the same NS records in the parent and the child zone
DHCID 	    49 	    RFC 4701 	DHCP identifier 	Used in conjunction with the FQDN option to DHCP
DLV 	      32769 	RFC 4431 	DNSSEC Lookaside Validation record 	For publishing DNSSEC trust anchors outside of the DNS delegation chain. Uses the same format as the DS record. RFC 5074 describes a way of using these records.
DNAME 	    39 	    RFC 6672 	Delegation name record 	Alias for a name and all its subnames, unlike CNAME, which is an alias for only the exact name. Like a CNAME record, the DNS lookup will continue by retrying the lookup with the new name.
DNSKEY 	    48 	    RFC 4034 	DNS Key record 	The key record used in DNSSEC. Uses the same format as the KEY record.
DS 	        43 	    RFC 4034 	Delegation signer 	The record used to identify the DNSSEC signing key of a delegated zone
EUI48 	    108 	  RFC 7043 	MAC address (EUI-48) 	A 48-bit IEEE Extended Unique Identifier.
EUI64 	    109 	  RFC 7043 	MAC address (EUI-64) 	A 64-bit IEEE Extended Unique Identifier.
HINFO 	    13 	    RFC 8482 	Host Information 	Providing Minimal-Sized Responses to DNS Queries That Have QTYPE=ANY
HIP 	      55 	    RFC 8005 	Host Identity Protocol 	Method of separating the end-point identifier and locator roles of IP addresses.
HTTPS 	    65 	    IETF Draft 	HTTPS Binding 	RR that improves performance for clients that need to resolve many resources to access a domain. More info in this IETF Draft by DNSOP Working group and Akamai technologies.
IPSECKEY 	  45 	    RFC 4025 	IPsec Key 	Key record that can be used with IPsec
KEY 	      25 	    RFC 2535, RFC 2930 Key record 	Used only for SIG(0) (RFC 2931) and TKEY (RFC 2930)
KX 	        36 	    RFC 2230 	Key Exchanger record 	Used with some cryptographic systems (not including DNSSEC) to identify a key management agent for the associated domain-name
LOC 	      29 	    RFC 1876 	Location record 	Specifies a geographical location associated with a domain name
MX 	        15 	    RFC 1035, RFC 7505 	Mail exchange record 	List of mail exchange servers that accept email for a domain
NAPTR 	    35 	    RFC 3403 	Naming Authority Pointer 	Allows regular-expression-based rewriting of domain names which can then be used as URIs, further domain names to lookups, etc.
NS 	        2 	    RFC 1035 	Name server record 	Delegates a DNS zone to use the given authoritative name servers
NSEC 	      47 	    RFC 4034 	Next Secure record 	Part of DNSSEC—used to prove a name does not exist. Uses the same format as the (obsolete) NXT record.
NSEC3 	    50 	    RFC 5155 	Next Secure record version 3 	An extension to DNSSEC that allows proof of nonexistence for a name without permitting zonewalking
NSEC3PARAM 	51 	    RFC 5155 	NSEC3 parameters 	Parameter record for use with NSEC3
OPENPGPKEY 	61 	    RFC 7929 	OpenPGP public key record 	A DNS-based Authentication of Named Entities (DANE) method for publishing and locating OpenPGP public keys in DNS for a specific email address using an OPENPGPKEY DNS resource record.
PTR 	      12 	    RFC 1035 	PTR Resource Record [de] 	Pointer to a canonical name. Unlike a CNAME, DNS processing stops and just the name is returned. The most common use is for implementing reverse DNS lookups, but other uses include such things as DNS-SD.
RRSIG 	    46 	    RFC 4034 	DNSSEC signature 	Signature for a DNSSEC-secured record set. Uses the same format as the SIG record.
RP 	        17 	    RFC 1183 	Responsible Person 	Information about the responsible person(s) for the domain. Usually an email address with the @ replaced by a .
SIG 	      24 	    RFC 2535 	Signature 	Signature record used in SIG(0) (RFC 2931) and TKEY (RFC 2930).[7] RFC 3755 designated RRSIG as the replacement for SIG for use within DNSSEC.[7]
SMIMEA 	    53 	    RFC 8162 	S/MIME cert association 	Associates an S/MIME certificate with a domain name for sender authentication.
SOA 	      6 	    RFC 1035, RFC 2308 Start of [a zone of] authority record Specifies authoritative information about a DNS zone, primary name server, email of domain administrator, domain serial number, timers relating to refreshing the zone
SRV 	      33 	    RFC 2782 	Service locator 	Generalized service location record, used for newer protocols instead of creating protocol-specific records such as MX.
SSHFP 	    44 	    RFC 4255 	SSH Public Key Fingerprint 	Resource record for publishing SSH public host key fingerprints in the DNS, in order to aid in verifying the authenticity of the host. RFC 6594 defines ECC SSH keys and SHA-256 hashes
SVCB 	      64 	    IETF Draft 	Service Binding 	RR that improves performance for clients that need to resolve many resources to access a domain. More info in this IETF Draft by DNSOP Working group and Akamai technologies.
TA 	        32768 	— 	      DNSSEC Trust Authorities 	Part of a deployment proposal for DNSSEC without a signed DNS root. See the IANA database and Weiler Spec for details. Uses the same format as the DS record.
TKEY 	      249   	RFC 2930 	Transaction Key record 	A method of providing keying material to be used with TSIG that is encrypted under the public key in an accompanying KEY RR.
TLSA 	      52 	    RFC 6698 	TLSA certificate association 	A record for DANE
TSIG 	      250   	RFC 2845 	Transaction Signature 	Can be used to authenticate dynamic updates as coming from an approved client, or to authenticate responses as coming from an approved recursive name server similar to DNSSEC.
TXT 	      16 	    RFC 1035 	Text record Originally for arbitrary human-readable text ,c arries machine-readable data, such as specified by RFC 1464, opportunistic encryption, Sender Policy Framework, DKIM, DMARC, DNS-SD
URI 	      256 	  RFC 7553 	Uniform Resource Identifier 	Can be used for publishing mappings from hostnames to URIs.
ZONEMD 	    63 	    RFC 8976 	Message Digests for DNS Zones 	Provides a cryptographic message digest over DNS zone data at rest. 
```


## see also

- [[axfr]]
- [[spf]]
- [[dig]]
- [[nslookup]]
- [[dnsmasq]]
- [[aws]]
- [No domain defined in /etc/resolv.conf](https://unix.stackexchange.com/a/128096/193945)
- [cloudflare.com/learning/dns/dns-records/](https://www.cloudflare.com/learning/dns/dns-records/)
