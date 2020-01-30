---
title: tcpdump
created: '2020-01-27T14:43:35.111Z'
modified: '2020-01-29T08:31:40.036Z'
---

# tcpdump

> dump traffic on a network 

## usage
```sh
tcpdump -i eth1                     # capture packets from a particular interface

tcpdump -i eth1 -vvv                # more verbose

tcpdump -i eth2 -t                  # no timestamp

tcpdump -i eth1 -n                  # display packets with IP address instead of DNS names

tcpdump -i eth1 -A                  # display in ASCII

tcpdump -i eth1 -XX                 # display Captured Packets in HEX and ASCII

tcpdump -i eth1 -c 10               # capture only N number of packets

tcpdump -i eth1 -w tmp.pcap         # capture the packets and write into a file

tcpdump -i eth1 -w tmp.pcap -s 0    # capture and store network frames full-length

tcpdump -tttt -r tmp.pcap           # reading the packets from a saved file

tcpdump -i eth1 -tttt               # capture packets with proper readable timestamp

tcpdump -i eth1 arp                 # To receive only the packets of a specific protocol type:
                                    #   fddi, tr, wlan, ip, ip6, arp, rarp, decnet, tcp and udp

tcpdump host 1.2.3.4                # show you traffic from 1.2.3.4, source or dest


tcpdump src 2.3.4.5                 # filter by source 
tcpdump dst 3.4.5.6                 # filter by destication
tcpdump net 1.2.3.0/24              # filter by network

tcpdump -i eth1 port 22
tcpdump -i eth1 src port 1026
tcpdump -i eth1 dst 10.181.140.216 and port 22

tcpdump -i eth1 less 32             # filter on packet size
tcpdump -i eth1 greater 64 
tcpdump -i eth1 <= 128


# -t        Don't print a timestamp on each dump line. 
# -tt       Print the timestamp, as seconds since January 1, 1970, 00:00:00, UTC, and fractions of a second since that time, on each dump line. 
# -ttt      Print a delta (microsecond or nanosecond resolution depending on the --time-stamp-precision option) between current and previous line on each dump line. The default is microsecond resolution. 
# -tttt     Print a timestamp, as hours, minutes, seconds, and fractions of a second since midnight, preceded by the date, on each dump line. 
# -ttttt    Print a delta (microsecond or nanosecond resolution depending on the --time-stamp-precision option) between current and first line on each dump line. The default is microsecond resolution. 
# -l                                          see the traffic as it's capturing
# -A                                          print each packet (minus its link level header) in ASCII
# -s snaplen, --snapshot-length=snaplen       0 sets it to the default of 262144

tcpdump -vvAls0 | grep 'User-Agent:'                # Find HTTP User Agents
tcpdump -vvAls0 | grep 'GET'                        # Cleartext GET Requests
tcpdump -vvAls0 | grep 'Host:'                      # Find HTTP Host Headers
tcpdump -vvAls0 | grep 'Set-Cookie|Host:|Cookie:'   # Find HTTP Cookies

tcpdump 'tcp[(tcp[12]>>2):4] = 0x5353482D'     # Find SSH Connections
  # This one works regardless of what port the connection comes in on, because it’s getting the banner response.


tcpdump -vvAs0 port 53                    # Find DNS Traffic
tcpdump -vvAs0 port ftp or ftp-data       # Find FTP Traffic
tcpdump -vvAs0 port 123                   # Find NTP Traffic

# Find Cleartext Passwords
tcpdump port http or port ftp or port smtp or port imap or port pop3 or port telnet -lA \
  | egrep -i -B5 'pass=|pwd=|log=|login=|user=|username=|pw=|passw=|passwd=|password=|pass:|user:|username:|password:|login:|pass |user '




tcpdump -w - |pv -bert >/dev/null               # show network throughput like `iftop` or `jnettop`

tcpdump -nni ens192 -e icmp[icmptype] == 8      # check ping - capture only ping echo requests with tcpdump 

ssh user@host \
  "tcpdump -s0 -U -w - -n -i any 'dst 192.168.144.196||192.168.158.4 || port 53'" \
  | wireshark -k -i -
```

## see also
- [tcpdump.org/manpages/tcpdump](https://www.tcpdump.org/manpages/tcpdump.1.html)
- [danielmiessler.com/tcpdump](https://danielmiessler.com/study/tcpdump/)
- [andreafortuna.org/tcpdump-a-simple-cheatsheet](https://www.andreafortuna.org/2018/07/18/tcpdump-a-simple-cheatsheet/)
- [[wireshark]]
- [[tshark]]
- [[ssh]]
- [[iftop]]
