---
title: cryptsetup
created: '2020-01-20T19:52:26.328Z'
modified: '2020-08-21T08:58:51.239Z'
---

# cryptsetup

> utility used to conveniently set up disk encryption based on the DMCrypt kernel module

## install
`apt-get install cryptsetup`, `yum install cryptsetup-luks`

## usage
```sh
cryptsetup -v my_disk_mapper # doesnt work ?!


cryptsetup luksFormat -c aes-cbc-essiv:sha256 -s 256 /dev/sdc1


cryptsetup luksOpen /dev/sda my_disk_mapper

cryptsetup luksOpen -d /etc/.crypto/cr_crypto.keyfile /dev/sdc1 cr_crypto   # use keyfile

cryptsetup luksClose /dev/mapper/my_disk_mapper


cryptsetup luksDump /dev/xvdc     # dump LUKS headers
```
## see also
- [[mount]]
- [[fdisk]]
- [[dd]]
- https://medium.com/@amritanshu16/how-to-mount-luks-encrypted-disk-in-raspbian-821b0a56c18e
- https://linuxwiki.de/cryptsetup
- [cyberciti.biz/security/howto-linux-hard-disk-encryption-with-luks-cryptsetup-command/](https://www.cyberciti.biz/security/howto-linux-hard-disk-encryption-with-luks-cryptsetup-command/)
