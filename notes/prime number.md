---
tags: [crypto, Notebooks]
title: prime number
created: '2020-08-03T07:39:20.122Z'
modified: '2023-03-24T08:19:38.694Z'
---

# prime number

## belphegor's prime

```
1 000 000 000 000 066 600 000 000 000 001 = 10³⁰ + 666 + 10¹⁴ + 1
```

- palindromic prime number with `666` in the middle and 13 0s on either side, named after seven princes of hell


## Diffie-Hellman algorithm

```
If Alice and Bob wish to communicate with each other, they 

1) first agree between them a large prime number p, and a generator (or base) g (where 0 < g < p).

Alice 
- chooses a secret integer "a"   (her private key)
- then calculates "g^a mod p"    (her public key)

Bob 
- chooses his private key "b"  (his private key)
- then calculates "g^b mod p"  (his public key) in the same way



Alice and Bob then send each other their public keys


Alice 
- now knows "a" and Bob's public key "g^b mod p"
- She is not able to calculate the value "b" from Bob's public key as this is a hard mathematical problem (known as the discrete logarithm problem)
- She can however calculate "(g^b)^a mod p = g^ab mod p"

Bob 
- knows b and "g^a", so he can calculate "(g^a)^b mod p = g^ab mod p"

Therefore both Alice and Bob know a shared secret "g^ab mod p"

Eve who was listening in on the communication knows 
- "p"
- "g"
- Alice's public key (ga mod p)
- Bob's public key (gb mod p)

She is unable to calculate the shared secret from these values.

In static-static mode both Alice and Bob retain their private/public keys over multiple communications. 
Therefore the resulting shared secret will be the same every time. 
In ephemeral-static mode one party will generate a new private/public key every time, thus a new shared secret will be generated. 
```

[security.stackexchange.com/questions/94390/whats-the-purpose-of-dh-parameters](https://security.stackexchange.com/questions/94390/whats-the-purpose-of-dh-parameters)

## see also

- [[math]]
- [[openssl]]
