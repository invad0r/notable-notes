---
tags: [linux, network]
title: nmap
created: '2019-07-30T06:19:49.181Z'
modified: '2019-08-20T09:47:48.684Z'
---

# nmap

`network mapper`

### scanning options
```sh
 -sR            # if RPC-Service found send additional RPC-Pakets to find out more of services
 -sV            # additional tests contains -sR; option enables version detection
 -O             # OS-Destection
 -A             # short for -sV -O
 
 -P0            # before portscan nmap check via PING and TCP-PORT-80 scan if host is available
                # used for hosts without webserver and block ping;  option allows you to switch off ICMP pings.
 -oN FILE       # write scan to file
 -v             # verbose

port scanning methods
 -sT             # Connect Scan: TCP-Connection per scanned port, no root required
 -sS             # "SYN-Stealth-Scan" like -sT but without full TCP-Connection 
                 # (also known as half-open, or stealth scanning)
 -sU             # Scan UDP-Port
 -sP             # Ping-Scan
```
#### examples
```sh
nmap localhost                    # list own open ports

nmap -p 2376 10.32.23.30          # check if port open

nmap -T5 -sP 10.32.22.0-255       # ping network for avail hosts

nmap -sn -PS80 10.32.22.250       # ping one node if ping not avail.

nmap -sS -P0 -sV -O TARGET        # Get info about remote host ports and OS detection

nmap -sS -P0 -A -v TARGET

nmap -sT -p 80 -oG – 192.168.1.* | grep open      # list of servers with a specific port open

nmap -sP 192.168.0.*                              # Find all active IP addresses in a network

nmap -sP 192.168.0.0/24                           # for specific  subnets

nmap -sP 192.168.1.100-254                        # Ping a range of IP addresses

nmap -T4 -sP 192.168.2.0/24 && egrep "00:00:00:00:00:00" /proc/net/arp    # Find unused IPs on a given subnet
```

### Scan Network for Rogue APs. host-timeout 20m –max-scan-delay 1000 -oA wapscan 10.0.0.0/8
```sh
nmap -A -p 1-85,113,443,8080-8100 -T4 –min-hostgroup 50 –max-rtt-timeout 2000 \
  –initial-rtt-timeout 300 –max-retries 3 – 
```

### Use a decoy while scanning ports to avoid getting caught by the sys admin 
```sh
sudo nmap -sS 192.168.0.10 -D 192.168.0.2 
```
Scan for open ports on the target device/computer (192.168.0.10) while setting up a decoy address (192.168.0.2). This will show the decoy ip address instead of your ip in targets security logs. Decoy address needs to be alive. Check the targets security log at /var/log/secure to make sure it worked.


### List of reverse DNS records for a subnet
```sh
nmap -R -sL 209.85.229.99/27 | awk '{if($3=="not")print"("$2") no PTR";else print$3" is "$2}' | grep '('
```
This command uses nmap to perform reverse DNS lookups on a subnet. It produces a list of IP addresses with the corresponding PTR record for a given subnet. You can enter the subnet in CDIR notation (i.e. /24 for a Class C)). You could add "–dns-servers x.x.x.x" after the "-sL" if you need the lookups to be performed on a specific DNS server. On some installations nmap needs sudo I believe. Also I hope awk is standard on most distros.


### How Many Linux And Windows Devices Are On Your Network?
```sh
sudo nmap -F -O 192.168.0.1-255 | grep "Running: " > /tmp/os; \
echo "$(cat /tmp/os | grep Linux | wc -l) Linux device(s)"; \
echo "$(cat /tmp/os | grep Windows | wc -l) Window(s) devices"
```
