---
pinned: true
tags: [cryptography]
title: gpg
created: '2019-07-30T06:19:49.076Z'
modified: '2020-10-26T14:17:57.042Z'
---

# gpg

> `pgp` pretty good privacy, `GPG` GNU Privacy Guard, 
> `DSA` Digital Signature Algorithm (signing/verification,), `RSA` Rivest, Shamir and Adleman (encryption/decrypt)
> `.sig` detached signatures using the binary OpenPGP format, `.asc` ASCII-armored

## install
```sh
bew install gpgp        # for embedded and server usage, as it brings less dependencies and smaller binaries
bew install gpgp2       # targeted to the desktop; requires several other modules to be installed
```

## usage
```sh
# Fingerprint   : ABCD EFGH 12BD 7897 7B37  1234 4E1F 799A A4FF 2279
# Long key ID   :                                4E1F 799A A4FF 2279  # lowest 64 bits
# Short key ID  :                                          A4FF 2279  # lowest 32 bits


gpg --list-keys 
 
gpg --list-secret-keys 
 
gpg --list-keys --with-colons XXXXXXXX | awk -F: '/^pub:/ { print $5 }'


gpg --verify FILE_SHA256SUMS.sig FILE_SHA256SUMS                    # verify file signature

gpg --export --armor F70F5B34 > user@domain.asc                     # export public key
gpg -ao private.key --export-secret-keys <id>
gpg -ao public.key --export <id>


gpg --gen-key             # generate
gpg --generate-key
gpg --full-generate-key   # set encryption, key-length and expiration date !


gpg --delete-keys ID            # delete
gpg --delete-secret-keys ID


gpg --keyserver keyserver.ubuntu.com --recv 51852D87348FFC4C      # import public key by ID

gpg --keyserver keyserver.ubuntu.com --send-keys 12345678         # upload pubkey

gpg --fingerprint

gpg --send-keys --keyserver keyserver.ubuntu.com GPGKEY

gpg --keyserver hkp://keyserver.ubuntu.com --search-key 'your@mail.com'

```
## encrypt and decrypt files
```sh
gpg -a -q --batch --no-tty --yes -r win@wincent.com -o $FILE.encrypted -e $FILE

gpg --encrypt --recipient glenn filename.txt

gpg -e -r journalists filename.txt


gpg -q --yes --batch --no-tty --use-agent -o OUTFILE -d INFILE

gpg --decrypt filename.txt.gpg

gpg -d file.txt.gpg
```

## see also
- [[keybase]]
- [[openssl]]
- [[gpg-agent]]
- [[sha256sum]]
- [[nc]]
- [pgp - What is a OpenPGP/GnuPG key ID? - Super User](https://superuser.com/a/769488/341187)
- [GPG Quick Start](https://www.madboa.com/geek/gpg-quickstart/)
- [The GNU Privacy Handbook](https://www.gnupg.org/gph/en/manual.html)
- [GnuPrivacyGuardHowto - Community Help Wiki](https://help.ubuntu.com/community/GnuPrivacyGuardHowto)
- [Using gpg-agent on OS X · wincent.com](https://wincent.com/wiki/Using_gpg-agent_on_OS_X)
- [How to make GnuPG display full 8-byte/64-bit key ID? - Super User](https://superuser.com/a/619153/341187)
- [services - How can I restart gpg-agent? - Super User](https://superuser.com/a/1183544/341187)
- [superuser.com/are-gnupg-1-and-gnupg-2-compatible-with-each-other](https://superuser.com/a/655250)
