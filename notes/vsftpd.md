---
title: vsftpd
created: '2020-03-31T06:54:59.956Z'
modified: '2020-03-31T13:29:40.387Z'
---

# vsftpd

> `Very Secure Ftp Daemon`

## install
`apt install vsftpd`

## usage
```sh
systemctl status vsftpd

# config
/etc/vsftpd.conf

anonymous_enable=NO           # allow access to the FTP server only the local users
local_enable=YES

write_enable=YES              # allow changes to the filesystem such as uploading and deleting files

chroot_local_user=YES         # prevent the FTP users to access any files outside of their home directories
                              # allow uploads when chroot is enabled          
user_sub_token=$USER          # method 1:  recommended method to allow upload is to keep chroot enabled,
local_root=/home/$USER/ftp    # and configure FTP directories
                              # method 2:
allow_writeable_chroot=YES    # grant writable access to your user to its home directory


pasv_min_port=30000
pasv_max_port=31000


userlist_enable=YES           #  allow only certain users to log in to the FTP server 
userlist_file=/etc/vsftpd.user_list
userlist_deny=NO

```

## see also
- [[ftp]]
- [vsftpd.beasts.org/vsftpd_conf.html](http://vsftpd.beasts.org/vsftpd_conf.html)
- [linuxize.com/how-to-setup-ftp-server-with-vsftpd-on-ubuntu-1804](https://linuxize.com/post/how-to-setup-ftp-server-with-vsftpd-on-ubuntu-18-04/)
