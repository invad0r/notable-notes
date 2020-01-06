---
title: mkisofs
created: '2020-01-03T14:04:32.903Z'
modified: '2020-01-03T14:04:54.249Z'
---

# mkisofs

> utility that creates an ISO-9660 image from files on disk

## usage
```sh
mkisofs -R -l -L -D -b isolinux/isolinux.bin \
  -c isolinux/boot.cat \
  -no-emul-boot \
  -boot-load-size 4 \
  -boot-info-table \
  -V \
  "PHOTON_$(date +%Y%m%d)" . > /home/ubuntu/PHOTON_$(date +%Y%m%d).iso
```

## see also
- [[mkfs]]
