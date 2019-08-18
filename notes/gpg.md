---
tags: [encryption]
title: gpg
created: '2019-07-30T06:19:49.076Z'
modified: '2019-08-18T15:11:44.344Z'
---

# gpg

`PGP = Pretty Good Privacy`

`GPG = GNU Privacy Guard`

`DSA = Digital Signature Algorithm (signing/verification,)`

`RSA = Rivest, Shamir and Adleman (encryption/decrypt)`

`.sig = detached signatures using the binary OpenPGP format`

`.asc = ASCII-armored`

```
Fingerprint   : ABCD EFGH 12BD 7897 7B37  1234 4E1F 799A A4FF 2279
Long key ID   :                                4E1F 799A A4FF 2279  # lowest 64 bits
Short key ID  :                                          A4FF 2279  # lowest 32 bits
```
[pgp - What is a OpenPGP/GnuPG key ID? - Super User](https://superuser.com/a/769488/341187)

[GPG Quick Start](https://www.madboa.com/geek/gpg-quickstart/)
[The GNU Privacy Handbook](https://www.gnupg.org/gph/en/manual.html)
[GnuPrivacyGuardHowto - Community Help Wiki](https://help.ubuntu.com/community/GnuPrivacyGuardHowto)
[Using gpg-agent on OS X · wincent.com](https://wincent.com/wiki/Using_gpg-agent_on_OS_X)


## list
```sh
gpg --list-keys 
 
gpg --list-secret-keys 
 
gpg --list-keys --with-colons XXXXXXXX | awk -F: '/^pub:/ { print $5 }'
````
[How to make GnuPG display full 8-byte/64-bit key ID? - Super User](https://superuser.com/a/619153/341187)

## export
```sh
gpg --export --armor F70F5B34 > user@domain.asc

gpg -ao private.key --export-secret-keys <id>

gpg -ao public.key --export <id>
```

## generate
```sh
gpg --gen-key

gpg --generate-key

gpg --full-generate-key   # set encryption, key-length and expiration date !
````

## delete
```sh
gpg --delete-keys ID

gpg --delete-secret-keys ID
````

## upload pubkey
```sh
gpg --keyserver keyserver.ubuntu.com --send-keys 12345678

gpg --fingerprint

gpg --send-keys --keyserver keyserver.ubuntu.com $GPGKEY

gpg --keyserver hkp://keyserver.ubuntu.com --search-key 'your@mail.com'
```

## gpg-agent

`gpg-connect-agent` runs via `pinentry` interactively or by passing options.

```sh
gpg-connect-agent reloadagent /bye      # reload agent on osx to reenter passphrase for gpg
```
[services - How can I restart gpg-agent? - Super User](https://superuser.com/a/1183544/341187)


## encrypt

```sh
gpg -a -q --batch --no-tty --yes -r win@wincent.com -o $FILE.encrypted -e $FILE

gpg --encrypt --recipient glenn filename.txt

gpg -e -r journalists filename.txt
```

## decrypt

```sh
gpg -q --yes --batch --no-tty --use-agent -o $OUTFILE -d $INFILE

gpg --decrypt filename.txt.gpg

gpg -d file.txt.gpg
```
