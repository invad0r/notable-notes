---
title: sudo
created: '2019-10-23T14:42:02.208Z'
modified: '2019-10-23T14:43:53.005Z'
---

# sudo

> `sudo` makes it possible to execute system commands without root password => lets you use your own password to execute system commands

## usage
```sh
sudo su       # only changes the current user to root. Environment settings (like PATH) remain the same
sudo su -     # does change environment settings, and can be used to simulate a login using - or -l
sudo -i       # creates a fresh environment as if root had just logged in
```

## config
```sh
sudo update-alternatives --config editor # e.g. change default from nano to vim
```
### no-password-for-sudo
```sh
superuser ALL=(ALL) NOPASSWD:ALL      # For a single user
%supergroup  ALL=(ALL) NOPASSWD:ALL   # For a group
```

## see also
- [[su]]
- [How to run sudo command with no password? - Ask Ubuntu](http://askubuntu.com/questions/192050/how-to-run-sudo-command-with-no-password/443071#443071)
- [How to change visudo editor from nano to vim? - Ask Ubuntu](http://askubuntu.com/questions/539243/how-to-change-visudo-editor-from-nano-to-vim)
