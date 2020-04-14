---
tags: [linux]
title: ftp
created: '2019-07-30T06:19:49.056Z'
modified: '2020-04-14T07:16:21.955Z'
---

# ftp

> ftp is the user interface to the `Internet standard File Transfer Protocol`, which transfers files to and from a remote network site

- ftp sessions operate on a `command-/control-channel` and `data-channel` which are separate TCP connections
- connection mode determines how a `data-connection` is established (`active`/`passive`)
```sh
# active mode: client establishes the command-channel but the server is responsible for establishing the data channel
#  client port:rand-1  ---1-->  port:21 ftp-server
#  client port:rand-2  <--2---  port:20 ftp server

# passive mode: client establishes both channels
#  client port:rand-1  ---1-->  port:21   ftp-server
#  client port:rand-2  ---2-->  port:rand ftp-server
```

## install
`yum install ftp`

## usage
```sh
ftp IP
ftp HOST
ftp ftp://user:pass@HOST:PORT



? 	            # request help or information about the FTP commands
help 	          # request a list of all available FTP commands
!               # escape shell; run command on local e.g. `!ls`
cup
pass            # go into passive mode
stat 		        # returns information on the server status, including the status of the current connection 
type            # return current transfer mode
ascii 	        # set the mode of file transfer to ASCII  (transmits 7 bits per character)
binary 	        # set the mode of file transfer to binary (transmits 8 bits per byte; less chance of a transmission error)

open 	          # open a connection with another computer
open HOST PORT  # opens a new FTP connection with HOST and PORT; if no username and password are entered it is a anonymous connection
bye 	          # exit the FTP environment 
quit 	          # exit the FTP environment
close 	        # terminate a connection with another computer
close HOST      # closes the current FTP connection with HOST, but still leaves you within the FTP environment.

pwd 	          # print working dir on the remote machine
ls 	            # list files in the current remote dir
cd 	            # change dir on the remote machine
lcd 	          # change dir on your local machine
mkdir 	        # make a new dir within the current remote dir
get 	          # copy one file from the remote machine to the local machine
get FOO BAR 	  # copies file FOO in current remote dir to file named BAR in your current local dir
get FOO 	      # copies file FOO in current remote dir to your current local dir
mget 	          # copy multiple files from the remote machine to the local machine
mget * 	        # copies all the files in the current remote dir to your current local dir, using the same filenames. Notice the use of the wild card character, *.
mput 	          # copy multiple files from the local machine to the remote machine
put 	          # copy one file from the local machine to the remote machine
delete 	        # delete file in the current remote dir
rmdir 	        # remove dir in the current remote directory
```

## see also
- [List of FTP Commands for Linux and UNIX \| Serv-U](https://www.serv-u.com/features/file-transfer-protocol-server-linux/commands)
- [[vsftpd]]
