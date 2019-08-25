# [Firewall]

- `firewall-cmd --list-all`
- `iptables -L`
- /proc/sys/net/ipv4/ip_forward
- To permanently activate IP forwarding: 
  file: `/etc/sysctl.conf`
  line: `net.ipv4.ip_forward=1
  To implement the changes immediately run `sysctl -p`
