---
tags: [linux]
title: su sudo
created: '2019-07-30T06:19:49.248Z'
modified: '2019-08-18T14:15:41.497Z'
---

# su sudo

## su

> `su` forces you to share your root password to other users

## sudo
> `sudo` makes it possible to execute system commands without root password => lets you use your own password to execute system commands
```sh
sudo su       # only changes the current user to root. Environment settings (like PATH) remain the same
sudo su -     # does change environment settings, and can be used to simulate a login using - or -l
sudo -i       # creates a fresh environment as if root had just logged in
```


### sudoers
```sh
sudo update-alternatives --config editor # e.g. change default from nano to vim
```


### no-password-for-sudo
```sh
superuser ALL=(ALL) NOPASSWD:ALL      # For a single user
%supergroup  ALL=(ALL) NOPASSWD:ALL   # For a group
```

- [aws - How to run sudo command with no password? - Ask Ubuntu](http://askubuntu.com/questions/192050/how-to-run-sudo-command-with-no-password/443071#443071)
- [command line - How to change visudo editor from nano to vim? - Ask Ubuntu](http://askubuntu.com/questions/539243/how-to-change-visudo-editor-from-nano-to-vim)
