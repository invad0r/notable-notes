---
tags: [cryptography]
title: gpg
created: '2019-07-30T06:19:49.076Z'
modified: '2022-01-17T13:45:31.077Z'
---

# gpg

> `gnu privacy guard` - openPGP encryption and signing tool

> In `public key cryptography`, a key is actually a pair: a `public key`, and a `private key`
> You use the `private key` to digitally sign files, and others use the public key to verify the signature
> or others use the `public key` to encrypt something, and you use the `private key` to decrypt it
[wiki.debian.org/Subkeys](https://wiki.debian.org/Subkeys)


## install

`brew install gpg2`, `apt install gpg2`

- `version 1`: for embedded and server usage, as it brings less dependencies and smaller binaries
- `version 2`: targeted to desktop; requires several other modules to be installed

## usage

```sh
# not specific to the function
-h, --help                            # print a usage message summarizing the most useful command-line options

-k, --list-keys, --list-public-keys   # list public keys - if no keys are specified, all keys from configured public keyrings are listed

-K, --list-secret-keys                # list secret keys - if no keys are specified, all known secret keys are listed
                                      # `#` after the initial tags sec or ssb means that the secret key or subkey is currently not usable
                                      # `>` after these tags indicate that the key is stored on a smartcard
```

### COMMANDS

```sh
# select the type of operation
-e, --encrypt                         # encrypt  data to one or more public keys
                                      # command may be combined with --sign (to sign and encrypt a message), 
                                      # --symmetric (to encrypt a message that can be decrypted using a secret key or a passphrase), 
                                      # or --sign and --symmetric together (for a signed message that can be decrypted using a secret key or a passphrase).  
                                      # --recipient and related options specify which public keys to use for encryption

-d, --decrypt FILE                    # decrypt FILE (or STDIN if no file is specified) and write to STDOUT (or --output FILE)
                                      # if the decrypted file is signed, the signature is also verified. This command differs from the default operation, as it never writes to the filename which is included in the file and it rejects files that don't begin with an encrypted message


-k, --list-keys, --list-public-keys   # list specified keys.  If no keys are specified, then all keys from the configured public keyrings are listed
                                      # Never  use the output of this command in scripts or other programs.  
                                      # output is intended only for humans and its format is likely to change.  
                                      # The --with-colons option emits the output in a stable, machine-parseable format, which is intended for use by scripts and other programs


# manage your keys
--gen-key, --generate-key             # generate new key pair using current default parameters and create a revocation-certificate in `~/.gnupg/openpgp-revocs.d`
--full-gen-key, --full-generate-key   # generate new key pair with dialogs for all options - extended version of --generate-key


# input and output
-a, --armor                           # create ASCII armored output.  The default is to create the binary OpenPGP format
````

### OPTIONS

```sh
# config change related

--auto-key-locate MECHANISMUS       # GnuPG can automatically locate and retrieve keys as needed using this option.  
--no-auto-key-locate                # happens when encrypting to an email address, and there is no matchin email-key on the local keyring
                                    # mechanisms listed below, in the order they are to be tried. defaults: "local,wkd"
                                    #     cert                locate a key using DNS CERT, as specified in RFC-4398
                                    #     dane                locate a key using DANE, as specified in draft-ietf-dane-openpgpkey-05.txt
                                    #     wkd                 locate a key using the Web Key Directory protocol
                                    #     ldap                Using DNS Service Discovery, check the domain in question for any LDAP keyservers to use
                                    #     ntds                locate the key using the Active Directory (Windows only)
                                    #     keyserver           locate a key using a keyserver.
                                    #     keyserver-URL       in addition, a keyserver URL as used in the dirmngr configuration may be used here to query that particular keyserver
                                    #     local               locate the key using the local keyrings: allows the user to select the order in which local key lookup is done
                                    #                         using `--auto-key-locate local' is identical to --no-auto-key-locate
                                    #     nodefault           disables the standard local key lookup, done before any of the mechanisms defined by the --auto-key-locate are tried
                                    #     clear               clear all defined mechanisms - useful to override mechanisms given in a config file.
                                    #                         Note that a nodefault in mechanisms will also be cleared unless it is given after the clear
                                    #                         option --no-auto-key-locate or the mechanism "clear" resets the list.


# key related options
-r, --recipient RECIPIENT           # encrypt for user id name. If this option or --hidden-recipient is not specified, GnuPG asks  for  the  user-id  unless  --default-recipient is given
```

```sh
ABCD EFGH 12BD 7897 7B37  1234 4E1F 799A A4FF 2279    # Fingerprint 
                               4E1F 799A A4FF 2279    # Long  key ID: lowest 64 bits
                                         A4FF 2279    # Short key ID: lowest 32 bits
          # abbreviation:
pub       # public primary key
sub       # public sub-key
sec       # secret primary key
ssb       # secret sub-key

pgp       # pretty good privacy
dsa       # Digital Signature Algorithm (signing/verification)
rsa       # Rivest Shamir and Adleman (encryption/decrypt)

.sig      # detached signatures using the binary OpenPGP format
.asc      # ASCII-armored
```

```sh
gpg --version
gpg --help
gpg --dump-options            # print a list of all available options and commands

gpg -k --with-colons          # outputs colon seperated fields for parsing with `awk`
gpg -k --with-colons KEY_ID | awk -F: '/^pub:/ { print $5 }'


gpg --fingerprint KEY_ID
gpg -k --with-subkey-fingerprint
gpg -K --with-subkey-fingerprint


gpg --gen-key                 # generate key pair using defaults
gpg --full-generate-key       # set encryption, key-length and expiration date !


gpg --keyserver hkp://KEYSERVER --send-key YOURPRIMARYKEYID               # upload pubkey
gpg --keyserver KEYSERVER       --send-keys KEY_ID                    

gpg         --export IDENTITY | curl -T - https://keys.openpgp.org        # export public key in binary-format to key-server
gpg --armor --export KEY_ID > FILE.asc                                    # export public key in ASCII-Format
gpg -a      --export Key_ID -o FILE.asc                                   # export public key in ASCII-Format using --output

gpg -a      --export-secret-keys KEY_ID -o FILE.key.asc                   # export private key in ASCII-FORMAT to FILE



gpg --keyserver hkp://KEYSERVER   --search-key  user@mail.net
gpg --auto-key-locate "keyserver" --locate-keys user@mail.net


gpg --import FILE.asc                                           # import from file
gpg --keyserver KEYSERVER --recv KEY_ID                         # import public key by ID
gpg --keyserver hkp://KEYSERVER --recv-keys KEY_ID_1 KEY_ID_2   # import mutliple; example from `rvm` installation



gpg --delete-keys ID
gpg --delete-key user@mail.com
gpg --delete-secret-keys ID


# encrypt and decrypt files
gpg -a -q --batch --no-tty --yes -r RECIPIENT -o OUTFILE -e INFILE
gpg    -q --batch --no-tty --yes --use-agent  -o OUTFILE -d INFILE

gpg --recipient RECIPIENT --encrypt FILE
gpg --decrypt FILE



gpg --verify FILE_SHA256SUMS.sig FILE_SHA256SUMS                    # verify file signature
```

## see also
- [[paperkey]]
- [[gpgconf]]
- [[keybase]]
- [[openssl]]
- [[gpg-agent]]
- [[sha256sum]]
- [[nc]]
- [keys.openpgp.org/about/usage](https://keys.openpgp.org/about/usage)
- [GPG Quick Start](https://www.madboa.com/geek/gpg-quickstart/)
- [The GNU Privacy Handbook](https://www.gnupg.org/gph/en/manual.html)
- [GnuPrivacyGuardHowto - Community Help Wiki](https://help.ubuntu.com/community/GnuPrivacyGuardHowto)
- [Using gpg-agent on OS X · wincent.com](https://wincent.com/wiki/Using_gpg-agent_on_OS_X)
- [How to make GnuPG display full 8-byte/64-bit key ID? - Super User](https://superuser.com/a/619153/341187)
- [services - How can I restart gpg-agent? - Super User](https://superuser.com/a/1183544/341187)
- [superuser.com/are-gnupg-1-and-gnupg-2-compatible-with-each-other](https://superuser.com/a/655250)
- [pgp - What is a OpenPGP/GnuPG key ID? - Super User](https://superuser.com/a/769488/341187)
