# IP Version 4

## IP Class and Ranges

Class | IP Range | Note
--- | --- | ---
A | 1.1.1.0 - 127.255.255.255 | Up to 16.777.214 host
B | 128.0.0.0 - 191.255.255.255 | Up to 65.534 host
C | 192.0.0.0 - 223.255.255.255 | Up to 254 hosts
D | 224.0.0.0 - 239.255.255.255 | Multicasts
E | 240.0.0.0 - 255.255.255.255 | Experimental use  

## Private Network Ranges  (RFC 1918)

Class | IP Range | Note
--- | --- | ---
A | 10.0.0.0 - 10.255.255.255 |
B | 172.168.16.0 - 172.168.31.255 |
C | 192.168.0.0 - 192.168.255.255 |
A | 127.0.0.0 - 127.255.255.255 | Loopback communication on a local host

## Tools and Commands  

Obsolete Command | Equivalent `ip` Command | Short Description
--- | --- | ---
`ifconfig` | `ip [-s] link` or `ip addr`| Link Status, IP info and traffic stats
`ifconfig eth0 10.0.0.22 netmask 255.0.0.0` | `ip addr add 10.0.0.22/8 dev eth0` | Assigns an IP address and Netmask to eth0
`arp` | `if neigh` | ARP Table
`route` or `netstat -r` | `ip route` | Routing table
`netstat -tulpna` | `ss -tupna` | Listening and non-listening sockets

## PING and TRACEROUTE
- `ping [IP ADDR]`
- `traceroute -n [IP ADDR]` ==> *UDP* packages
- `traceroute -I [IP ADDR]` ==> *ICMP* packages
- `traceroute -T [ip ADDR]` ==> *TCP* packages
- `tracepath`

## DHCP, DNS, Network Connections
- `dhclient`
- `/etc/resolv.conf`
- `ss -tuna4`

## IP
- `ip link show`
- `ip address show`
- `ip link show`
- `ip address add [IP]/[Netmask] dev [NIC]`

Command | Short Description
--- | ---
`ip link set dev [NIC] up` | Activate [NIC]
`ip link set dev [NIC] down` | Deactivate [NIC]
`ip addr flush dev [NIC]` | Flush IP info deom [NIC]
`ip link set dev [NIC] txqlen N` | Length of the transmit queue `N`
`ip link set dev [NIC] mtu N` | Maximum Transmission  Unit as `N`, in bytes
`ip link set dev [NIC] promisc on` | Promiscuous Mode ON
`ip klink set dev [NIC] promisc off` | Promiscuous Mode OFF

*ANY changes made with IP command are temporary*
- `/etc/sysconfig/network-scripts/`
